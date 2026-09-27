---
name: xianmu-ims
description: 闲沐 IMS 库存管理操作技能。当用户要查询或管理库存、物品档案、入库、出库、移库、盘点、库存预警、供应商与库位信息时使用——通过用户自建的闲沐 IMS 实例 REST API 完成。触发词：库存、入库、出库、移库、盘点、预警、库存查询、闲沐、IMS。
---

# 闲沐 IMS 库存操作

通过用户部署的闲沐 IMS 实例（局域网/NAS/本机）的 REST API 查询与操作库存。

## 使用前提

开始前向用户确认两件事（本会话内记住即可）：

1. **实例地址**（BASE，如 `http://<你的实例地址>:8066`，实例本机可用 `http://127.0.0.1:8066`）
2. **API Token**（可选但强烈建议）：用户在闲沐 IMS「设置 → API Token」新建，形如 `xmt_` 开头，明文只显示一次。Token 决定操作权限（viewer 只读 / member 可写 / admin 管理），并有每分钟 60 次限流保护。

> 单人模式下实例不强制认证，无 Token 也能调用；但仍建议用户提供 Token（限流保护 + 操作审计）。

## 接入方式选择

闲沐 IMS 同时提供两种方式，消费同一套开放 API、同受 Token 限流与专业版 `feature.api` 权益约束（无权益调用返回 403 `EDITION_REQUIRED`），二选一即可：

- **客户端支持远程 HTTP MCP 时，优先用 MCP**：服务端原生 `BASE + /api/mcp`（Streamable HTTP），只填「实例地址 + Token」即得精选 **27 个工具**（读 11 / 写 16），零本地依赖，NAS / 远程实例同样可用。配置见文末「参考」。
- **客户端不支持（或不方便改配置）时，用本技能的 REST 方式**：即下文全部内容。

## 请求约定

- 所有接口前缀 `BASE + /api/v1`；认证用请求头 `Authorization: Bearer <Token>`。
- 成功响应是信封：`{"code": "OK", "message": "ok", "data": <业务数据>}` —— **业务数据一律从 `data` 里取**。
- 失败响应：`{"code": "<错误码>", "message": "<说明>", "details": …}`，HTTP 状态码同时给出。常见错误码：

| 错误码 | 含义 | 处理建议 |
|---|---|---|
| AUTH_REQUIRED (401) | Token 缺失/无效/已吊销 | 请用户重新创建 Token |
| FORBIDDEN (403) | 角色权限不足 | 写操作需要 member 及以上；报废（scrap）出库需要 admin；向用户说明 |
| EDITION_REQUIRED (403) | 需要专业版权益 | 提示此功能属专业版 |
| READONLY_MODE（仅 MCP） | 实例处于只读模式 | URL 带 `?mode=readonly` 或演示环境时写操作不可用；确认用户是否需要只读，再决定是否改用普通地址 |
| NOT_FOUND (404) | 物品/库位/任务不存在 | 换关键词重查 |
| DUPLICATE_ITEM (409) | 建档查重命中 | 向用户展示疑似重复项，确认后可用 `force: true` 强制建档 |
| OUT_OF_STOCK (409) | 库存不足 | 报告现有数量，不要擅自降低出库数 |
| RATE_LIMITED (429) | 超过 60 次/分 | 等待几十秒重试，减少请求频率 |

- 分页统一参数 `page` / `page_size`，服务端上限 200，**建议 ≤50** 避免撑爆上下文。

## 核心工作流

细节与完整参数见 [references/api.md](references/api.md)。

### 1. 查库存
```
GET /api/v1/items?q=M3&low_stock=false&page=1&page_size=20
```
拿到列表后，需要某物品在各库位的分布再调 `GET /items/{id}/stocks`；需要流水调 `GET /stock/records?item_id={id}`。先精确后模糊：优先用型号/内部编号查询，减少分页轮次。

### 2. 入库（含建档）
- 已有物品：`POST /api/v1/stock/inbound`，body 至少给 `item_id` + `quantity`（+`total_price`、`supplier_id`、`location_id`、`remark` 按需）。
- 新物品一步到位：body 里不给 `item_id`，给 `new_item`（内联建档字段：`name`/`model`/`type`/`location_id`/`unit` 必填）+ `quantity`。
- 建档前先 `GET /items?q=<型号>` 查重，命中 `DUPLICATE_ITEM` 时把候选给用户确认。

### 3. 出库 / 移库 / 调整
- `POST /stock/outbound`：`item_id` + `quantity` + `purpose`（project/consume/scrap，scrap 需 admin）。
- `POST /stock/transfer`：`item_id` + `to_location_id`（多位置物品可加 `from_location_id`）。
- `POST /stock/adjust`：`item_id` + `counted_qty`（按实盘数调整，生成 adjust 流水）。

### 4. 盘点 / 预警
- 盘点：`GET /stocktakes` 找到进行中的任务 → `GET /stocktakes/{task_id}/lines?filter=pending` 看待盘行 → `PUT /stocktakes/{task_id}/lines/{line_id}` 录 `counted_qty`。**创建/确认/取消任务留给用户在界面做**。
- 预警：`GET /alerts`（默认只回 active）→ 处理完后 `POST /alerts/{id}/acknowledge` 确认。

### 5. 图片与资料
- 加图片：`POST /items/{id}/attachments`（multipart，`file_type=image`，≤20MB）；调整顺序/封面用 `PUT /items/{id}/attachments/order`（ids 须覆盖全部附件，第一张为封面）。
- 加资料：链接用 `POST /items/{id}/docs`（后台抓取，稍后 `GET /docs?item_id=` 看结果）；本地文件用 `POST /docs/upload`（后缀白名单 pdf/docx/txt/md/png/jpg/xlsx/csv/pptx/zip 等）。
- 一份资料可关联多个物品（多对多）：改显示名用 `PATCH /docs/{doc_id}`（body `{"title": "…"}`）；追加关联用 `POST /docs/{doc_id}/items`（body `{"item_id": 123}`，幂等）；解除关联用 `DELETE /docs/{doc_id}/items/{item_id}`（资料本身保留）。注意 `GET /docs?item_id=` 的含义是「**包含**该物品的资料」，不等于唯一归属；列表行里 `items[]` 才是全部关联物品。
- 删除物品**不会**删除它名下的资料，只会解除关联（资料降级为未关联的全局资料）；资料被删除只有 `DELETE /docs/{doc_id}` 一条路径。
- 删除图片/资料均为不可恢复操作，先向用户确认再调用。

## 护栏（必须遵守）

1. **写操作前先复述确认**：入库/出库/移库/调整/建档前，向用户复述「物品 + 数量 + 目标库位」，得到确认再调用。用户指令已非常明确时可省略复述直接执行。
2. **禁触端点**：不要调用设置（`/settings`，含 AI 密钥）、授权（`/license`）、Token/Webhook 管理、用户管理等系统端点；也不要调用物品删除/物理删除/并库/停用（`DELETE /items/{id}`、`/purge`、`/merge`、`/disable`）——这些留给用户在界面操作。
3. **出错不删数据**：有流水的物品不可删除只能停用；写错了提示用户在界面用「冲正」功能回退，Agent 不要自行尝试补救性反向操作。
4. **一次一步**：批量入库/出库逐条执行，每条之间检查响应；某条失败（如 OUT_OF_STOCK）就停下报告，不要跳过继续。
5. **数量与单位照抄用户口径**，不主动换算；价格字段留 0 表示未计价。

## 参考

- 完整端点速查（参数/请求体/响应示例）：[references/api.md](references/api.md)
- 机器可读接口定义：`GET BASE/api/openapi.json`（Swagger UI：`BASE/api/docs`）
- 变更感知：库存/预警/采购事件可由用户在「设置 → Webhook」订阅（HMAC 签名推送），适合接 n8n 等自动化平台
- 原生 MCP 接入（服务端 `BASE + /api/mcp`，Streamable HTTP）：**已上线**（专业版 `feature.api` 权益）——客户端支持远程 HTTP MCP 时优先用，请求头同样填 `Authorization: Bearer xmt_…`；URL 追加 `?mode=readonly` 即进入只读模式（写工具调用返回 `READONLY_MODE`），演示环境自动强制只读。工具面 27 个（读 11 / 写 16），覆盖查询、出入库、移库、盘点、预警与图片资料管理；不含物品删除/并库/设置类端点
