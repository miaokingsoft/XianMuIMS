<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://ims.miaoking.com/github/logo-horizontal-dark.png">
  <img src="https://ims.miaoking.com/github/logo-horizontal.png" alt="闲沐 IMS · AI 智能物资管理平台" width="360">
</picture>

### 跑在自己电脑、NAS 或树莓派上的物资管理系统

**1 张截图 = 10 秒入库** · 数据存在自己设备里 · 免费版永久免费

[**下载 Windows 版**](https://github.com/miaokingsoft/XianMuIMS/releases/latest/download/XianMuIMS-setup.exe) ·
[在线体验](https://imsdemo.miaoking.com) ·
[官网](https://ims.miaoking.com) ·
[全部版本](../../releases)

</div>

---

## 先在线体验

不想先装？**[请点击这里访问在线演示](https://imsdemo.miaoking.com)** 随时可进，以**专业版全功能**运行（含多人协作 / 开放 API / 审计日志），无需注册。

演示账号 `demo`，密码见演示站公告。演示数据每日凌晨重置，请勿存放真实物品信息。

![闲沐 IMS 主界面：物品图片化卡片视图、分类侧栏与检索](https://ims.miaoking.com/github/shots/hero.webp)

---

## 它解决什么问题

用 Excel、记事本或脑子记账，通常卡在这五件事上：

| 烦心事 | 闲沐 IMS 怎么做 |
|---|---|
| **重复买** —— 不知道还剩几个 | 库存台账以流水为事实源，低于安全线自动提醒 |
| **找不到** —— 记了名字不知道放哪 | 区域 → 柜 → 格位三级位置地图，中文全文检索秒到 |
| **懒得记** —— 建档太麻烦，录一件要敲半天 | 购物截图丢进去，AI 认出品名/型号/数量/价格，确认即入库 |
| **记了没用** —— 手册、链接、替代型号散在网盘和聊天记录 | 数据手册、购买链接、替代型号候选随物品档案走 |
| **被打断** —— 正干着活，查个库存还得切出去点四五下 | 接入 WorkBuddy 等 AI 智能体（MCP），说一句话直接办，详见下文「用 AI 智能体管库存」 |

适合：创客 / 独立开发者（元器件、模块、3D 打印耗材）、小工作室（摄影、模型、手工器材）、实验室与教学（试剂、设备、资料可追溯）、家庭个人（工具、耗材、装饰）。

---

## 核心能力

### 一张截图，10 秒入库

购物截图直接 `Ctrl+V` 粘贴（或手机扫码传图），视觉大模型解析出品名、型号、数量、单价，**一图多物**逐行确认入库——一笔不超过 10 秒。也支持淘宝 / 天猫订单 xlsx 批量导入。

![AI 贴图入库：粘贴商品图，AI 解析后逐行确认建档入库](https://ims.miaoking.com/github/shots/feat-ai-confirm.webp)

### 物品档案与库存台账

图片、参数、库存、流水一页看全；多图附件拖拽排序，首图即封面；自定义字段想加就加，照样搜得到。

![物品档案：快速编辑抽屉，型号 / 系列可 AI 推荐](https://ims.miaoking.com/github/shots/feat-item.webp)

### 位置地图

区域 → 柜 → 格位三级地图，按图索骥；同一物品可分布在多个位置；拖一下物品卡就完成移库。

![位置地图：三级导航与右侧物品抽屉](https://ims.miaoking.com/github/shots/feat-map.webp)

### 标签打印

适配精臣 B21Pro 热敏标签机直印物品码 / 位置码，贴上即扫、扫码直达；标签长什么样，用拖拽设计器自己排。

![标签打印：拖拽设计器排版专属标签，直连精臣 B21Pro 真实预览](https://ims.miaoking.com/github/shots/feat-labels.webp)

### 项目管理与 BOM 缺料

导入项目 BOM，自动比对库存标出缺口（充足 / 部分缺 / 完全缺），缺料一键生成采购单，按行领用出库并统计用料成本。

![项目管理：BOM 与库存逐行比对，缺口与用料成本一目了然](https://ims.miaoking.com/github/shots/feat-project.webp)

### 资料库 · 手册 / 购买链接 / 替代型号

每个物品都能挂数据手册 PDF、购买链接（自动抓取存档并生成 AI 整理版）、替代型号候选——找料时不用再翻网盘、书签和聊天记录。

![物品详情：手册与替代型号](https://ims.miaoking.com/github/shots/feat-detail.webp)

### 还有这些

- **精准查找** —— 中文全文检索（SQLite FTS5 trigram / MySQL 8 FULLTEXT ngram 双引擎），规格参数与自定义字段平铺进检索列，记不住型号也搜得到
- **扫码即达** —— 摄像头扫码 + USB 扫码枪双通道，物品码 / 位置码为 http 深链二维码，手机系统相机直接可扫
- **库存与流水** —— 入库 / 出库 / 消耗 / 借还 / 移库 / 盘点，支持冲正，历史全程可追溯
- **预警与到期提醒** —— 耗材保质期临期、仪器校准到期、低库存、逾期未还，提前提醒你
- **手机扫码传图** —— 桌面端生成二维码，手机扫码进入上传页拍照回传，人不用离开货架
- **盘点** —— 任务 / 实盘录入 / 差异对比，确认后自动生成调整流水
- **AI 批量补全 / AI 取图** —— 老档案一键补齐空缺字段（只填空缺，不覆盖人工填写）；没图的物品让 AI 找候选图手选
- **通知渠道** —— 邮件 / 钉钉 / 企业微信 / Telegram，支持每日与每周摘要
- **PWA 手机端** —— 手机浏览器打开就能用，可像 App 一样装到桌面；静态资源与读接口离线可查。**注意：激活与更换设备需联网访问一次官方门户**完成设备绑定，之后日常使用全程离线
- **备份导出** —— 每日定时自动备份，CSV / Excel / JSON 导入导出
- **部署形态** —— Windows 安装包双击即用（含常驻工具箱）；NAS / 树莓派 / 云服务器走 Docker 一条命令；数据库 SQLite 单文件零运维，或 MySQL 8（两者任选、切换不迁移数据）
- **AI 智能体接入（MCP，免费版可用）** —— 整库接入 WorkBuddy 等 MCP 智能体，说人话查库存、办出入库、跑盘点，支持只读模式；对智能体说一句话还能让它替你装好并接入；详见下文「用 AI 智能体管库存」

> **AI 能力需自配 API Key（BYOK）**：软件不附带密钥、不额外收费，用量由你自己控制；兼容 OpenAI 协议，也可接本地 Ollama 模型。

---

## 用 AI 智能体管库存：说句话，全办妥（MCP）

闲沐 IMS 内置 MCP（Model Context Protocol）服务端，**免费版即可使用**（免费版实例条目上限 50 件，超限后的新增会提示升级，查询不受影响）：把整个库存系统接入 [WorkBuddy](https://www.workbuddy.cn) 这类 AI 智能体，**软件界面不用打开，中文说一句话，AI 直接查库存、办出入库、记借还、盯预警、跑盘点**。工具面已达 **67 个**（读 21 / 写 46）。

<!-- TODO: 拍一张 WorkBuddy 真实对话截图，存到官网托管目录（website/github/shots/feat-mcp.webp，与门面仓 assets/shots/ 同内容）后取消下面注释 -->
<!-- ![WorkBuddy 对话窗口：说人话，AI 直接操作库存系统](https://ims.miaoking.com/github/shots/feat-mcp.webp) -->

### 对话即操作

> **你**："ESP32-S3 摄像头开发板还剩几个？"
>
> **WorkBuddy**："共 2 个，位于主工作区/零件柜/传感器模块/A/01/03。另外提醒：十字扁平头螺丝低于安全线（剩 6 个 / 安全线 10）。"

AI 会主动补上下文——你问库存，它顺手把预警也报了。

> **你**："昨天到的 FFC 排线，16P 反向那款，5 条，入到 A01 的 07 格。"
>
> **WorkBuddy**："已入库：FFC/FPC 软排线（16P 反向 0.5mm 100mm），数量 +5，位置 /A/01/07，当前库存 10 条。"

> **你**："电磨机借给老王了，下周六还。"
>
> **WorkBuddy**："已登记借出 1 台，预计归还下周六，逾期会进预警。"

> **你**："温湿度监测盒那个项目还缺什么料？"
>
> **WorkBuddy**："BOM 共 9 行，缺 5 行，缺口最大的 2.54mm 排针需 20 库存 1，杜邦线需 1 卷库存 0。要把缺口加入采购清单吗？"
>
> **你**："加。"
>
> **WorkBuddy**："已加入采购清单，共 5 项待购。"

同样的活儿在界面里是：打开软件 → 搜索 → 点详情 → 填单 → 选位置 → 确认；在对话里是一次开口。多步操作也能串着说——"把缺口加入采购清单"在界面上是 BOM 比对 → 勾选 → 跳采购页 → 逐项添加，在对话里就一个"加"字。

### 接入后 AI 能做什么（67 个工具）

不是只读的玩具接口，是完整的操作面（下表为主要分类）：

| 类别 | 覆盖能力 |
|---|---|
| **查询** | 物品搜索、物品详情、多库位分布、全局流水、分类 / 库位树 / 供应商、预警列表、盘点任务与差异、资料库检索 |
| **库存操作** | 入库（可顺带建档）、出库（领用 / 消耗 / 报废）、移库、按实盘数调整 |
| **档案与附件** | 建物品档案、更新字段、上传图片 / 手册等附件、附件排序（首图即封面） |
| **资料库** | 添加资料链接（后台自动抓取正文）、上传资料文件、一份资料关联多个物品 |
| **采购与项目** | 采购清单加入与状态流转、到货入库确认、BOM 缺料比对与一键加入采购、项目领用出库 |
| **借还与盘点** | 借出登记与归还、盘点任务实盘录入 |
| **初始化引导** | 新实例分阶段引导建分类与位置（对 AI 说「帮我初始化闲沐 IMS」即可） |

**内置护栏，放心放手**：报废出库需管理员角色；流水冲正不开放给智能体（记错账请登录界面处理，防止 AI 误操作连环放大）；MCP 另有 `?mode=readonly` 只读模式——只让 AI 查、不让 AI 改，不确定就先只读跑几天。

### 方式 A · 对智能体说一句话：装好 + 接入全自动（推荐）

把下面这句触发语发给任意支持 MCP 的桌面智能体（WorkBuddy / Claude Desktop / Cursor / Qoder / TRAE / CodeBuddy 等），**还没装软件也适用**：

> 读取 https://ims.miaoking.com/skill.md 并按照其中的说明，安装闲沐 IMS 并连接它的 MCP 服务器。

（英文触发语：`Read https://ims.miaoking.com/skill.md and follow the instructions to set up XianMu IMS and connect its MCP server.`）

智能体会读取官方接入引导（[skill.md](https://ims.miaoking.com/skill.md)，自足文档，无需抓取其他网页），自主完成六步：① 下载安装并启动 → ② 引导你在网页端「设置 → API Token」创建 Token → ③ 写入客户端 MCP 配置 → ④ 验证连接 → ⑤ 问答式初始化分类与位置 → ⑥ 给你使用指引。

全程只有两件事由你**亲手**完成，智能体不代劳：点各环节的确认弹窗（SmartScreen「仍要运行」、UAC、客户端「允许连接」——都是安全机制，不是报错），以及 API Token 的创建与保管。引导文档只含无副作用的操作，智能体卡住时按文档末尾附录 A 的人工清单照做即可，不会卡死。

### 方式 B · 手动接入：五分钟，一次配好

前提一个 API Token（登录系统 →「**设置 → API Token**」→ 新建，`xmt_` 开头，明文只显示一次，请立即保存）。只想先试试？可以跳过——下面第 2 步的示例配置就是演示站，照抄即连。

**第 1 步 · 打开连接器设置**：WorkBuddy 左侧导航「**专家 · 技能 · 连接器**」→「**连接器**」，点「**自定义连接器**」（或在「MCP 服务管理」弹窗右上角点「**＋ 添加 MCP**」）。

**第 2 步 · 写入配置**：编辑配置文件 `%USERPROFILE%\.workbuddy\mcp.json`，加入以下内容并**保存**（示例直接用演示站配置，照抄就能连；自建实例把 `url` 换成实例地址、Token 换成自己的）：

```json
{
  "mcpServers": {
    "xianmu-ims": {
      "url": "https://imsdemo.miaoking.com/api/mcp",
      "headers": {
        "Authorization": "Bearer xmt_ims-demo-token-2026"
      }
    }
  }
}
```

**第 3 步 · 确认连接**：回到「MCP 服务管理」列表，`xianmu-ims` 显示**绿点**、工具列表全部「已启用」即接入成功；列表里可随时启停、刷新或删除（不同版本工具数会随功能增加）。

**第 4 步 · 验证**：新开对话先试一句只读的——**现在有多少条低库存预警？**

> **零成本试用**：上面的配置就是演示站，照抄即可连上——演示实例强制只读，随便查不翻车；要体验完整写入能力，把 `url` 换成你自己实例的地址。

地址填法：必须是**运行 WorkBuddy 的那台机器**能访问到的地址——同局域网填 NAS / 电脑的内网 IP（如 `192.168.1.10:8066`），客户端装在实例本机才可用 `127.0.0.1`。MCP 走 Streamable HTTP，零本地依赖，NAS / 远程实例照样可用。

### 其他 AI 客户端同样能接

同一套「地址 + Token」配置（类型选 **Streamable HTTP**，不要选 stdio / 本地命令类型）也适用于 Claude Desktop、Claude Code、Cursor、Qoder、Cherry Studio、ZCode 等，分客户端配置示例见 [API 文档](https://ims.miaoking.com/docs/api.html)。不想配 MCP 的编码类 Agent，也可以改用随发布包附带的 [`xianmu-ims` Skill 文件夹](skill/xianmu-ims)（安装版位于安装目录 `skill\xianmu-ims\`，Windows 默认 `%LOCALAPPDATA%\Programs\XianMuIMS\skill\xianmu-ims\`），效果等价。

新装实例第一次用，直接对智能体说「**帮我初始化闲沐 IMS**」即可：随包技能 [`skill/xianmu-ims/`](skill/xianmu-ims)（或方式 A 的在线引导）会先检测实例现状，再通过几轮场景化问答（家庭收纳 / 极客硬件库 / 手作创作 / 办公物资 / 搬家整理 / 小仓库等）生成分类与位置配置预览，你确认后自动写入 MCP——分类、位置一次配好，随时可中断续跑。

---

## 系统要求

| 形态 | 要求 |
|---|---|
| Windows 安装版 | Windows 10 / 11 **64 位**；不需要 Python / Node / 数据库 |
| NAS / 树莓派 / Docker | 群晖、QNAP、树莓派（**64 位系统**，走 arm64 镜像）或任意 Docker 环境（单容器）；Mac / Linux 同路径 |
| 数据库（可选） | 默认 SQLite 单文件；也可选 MySQL 8 |
| 浏览器 | Chrome / Edge / Safari / Firefox 等现代浏览器；手机端走 PWA |
| 标签打印（可选） | 精臣 **B21Pro** 标签机 + 精臣官方 USB 驱动 + 闲沐本机打印服务（仅 Windows） |

---

## 下载

### Windows 安装版

**[⬇ 下载 XianMuIMS-setup.exe](https://github.com/miaokingsoft/XianMuIMS/releases/latest/download/XianMuIMS-setup.exe)**

- 适用 **Windows 10 / 11 64 位**，双击安装即用，**无需**装 Python / Node / MySQL
- 自带常驻工具箱（服务启停、开机自启、端口管理、数据库切换），**无需管理员权限**
- 下载无需注册、不做邮箱校验；免费版永久免费，不激活也照常使用
- 让 AI 替你装：对桌面智能体说一句话，自动下载安装并接入 MCP，见上文「用 AI 智能体管库存」
- 历史版本与更新说明见 [Releases](../../releases)；官网下载入口：[ims.miaoking.com](https://ims.miaoking.com/#download)

**校验下载完整性（推荐）**：与安装包同目录发布同名 `.sha256` 文件。

```powershell
# Windows PowerShell：把结果与 Releases 页的 .sha256 文件对比，应完全一致
Get-FileHash .\XianMuIMS-setup.exe -Algorithm SHA256
```

> **关于 SmartScreen 提示**：安装包暂未购买代码签名证书，Windows 首次运行可能提示"已保护你的电脑"。这不是病毒告警，而是对"未签名程序"的通用提示——可以点「更多信息 → 仍要运行」，或先用上面的 SHA256 校验确认文件未被篡改。介意的话也可以改用 [NAS / 树莓派 / Docker 部署](https://ims.miaoking.com/docs/deploy.html)。

### NAS / 树莓派 / Docker 部署

群晖、QNAP、树莓派（64 位系统）或任意 Docker 环境：一条 `docker compose up` 启动，首次自动建表迁移；数据全在自己设备本地的数据库里。图文步骤见 [部署指南](https://ims.miaoking.com/docs/deploy.html)。Mac、Linux 与树莓派同样通过 Docker 运行。

镜像发布在腾讯云公有仓库 `ccr.ccs.tencentyun.com/xianmuwork/xianmuims`（**公有、免登录**），同时提供 x86（amd64）与 ARM（arm64）两种架构——**树莓派（64 位系统）走 arm64，已在实机验证**。电脑 / 树莓派 / 云服务器上整行复制粘贴即可起服务：

```bash
mkdir -p xianmu-ims && cd xianmu-ims && curl -fsSLO https://down.wwzu.com/release/docker/docker-compose.yml && { DC=docker-compose; docker compose version >/dev/null 2>&1 && DC="docker compose"; $DC up -d; }
```

Windows（已装 Docker Desktop，PowerShell 里执行）：

```powershell
mkdir xianmu-ims; cd xianmu-ims; iwr https://down.wwzu.com/release/docker/docker-compose.yml -OutFile docker-compose.yml; docker compose up -d
```

> 内网 / 无外网环境（拉不到镜像）：请**联系客服**，由客服一对一提供交付与激活方案。

---

## 文档与常见问题

| 文档 | 内容 |
|---|---|
| [快速开始](https://ims.miaoking.com/docs/quick-start.html) | 5 分钟跑起来：安装、初始化向导、贴图入库第一件物品 |
| [用户手册](https://ims.miaoking.com/docs/manual.html) | 完整功能详解：入库、盘点、位置地图、标签设计器、资料库、AI 能力 |
| [部署指南](https://ims.miaoking.com/docs/deploy.html) | Docker / 群晖 / 树莓派部署、备份恢复与升级全流程 |
| [API 文档](https://ims.miaoking.com/docs/api.html) | 开放接口、Webhook 与智能体接入 |
| [常见问题 FAQ](https://ims.miaoking.com/faq.html) | 免费版限制、价格与授权、设备绑定与退款、标签打印安装 |

**高频问题**

- **是云端服务吗？** 不是。跑在你自己的电脑、NAS 或树莓派上，数据存本地，无云端依赖。
- **免费版有什么限制？** 单人 1 个账号 + 50 件物品条目。注意算的是**条目数**（同一型号算一件），库存数量不限——某个型号库存 500 个也只占 1 件额度。
- **AI 功能要另外付费吗？** 不另外付费，免费版与专业版都含；自配 API Key，用量自己控制。
- **换电脑怎么办？** 门户自助解绑旧设备后重新激活即可，不重复收费（需联网访问一次门户）。
- **能用 WorkBuddy / Claude 这类 AI 助手直接管库存吗？** 能。免费版与专业版都内置 MCP 服务端（67 个工具，含只读模式），WorkBuddy、Claude Desktop、Cursor 等填「实例地址 + Token」即可接入，或对智能体说一句话自动装好并接入（见上文「用 AI 智能体管库存」）；免费版实例条目上限 50 件，专业版无此限制。

---

## 反馈与支持

- **Bug 与功能建议** → [提交 Issue](../../issues)（附版本号、系统与复现步骤，越具体越好）
- **使用问题** → 先查 [FAQ](https://ims.miaoking.com/faq.html) 与 [用户手册](https://ims.miaoking.com/docs/manual.html)
- **客服邮箱** [kf@wwzu.com](mailto:kf@wwzu.com) · **官网** [ims.miaoking.com](https://ims.miaoking.com)

> 提交 Issue 时**请勿粘贴激活码、License 文件内容、API Token、订单号或任何密钥**——这些属于敏感信息，公开 Issue 会被所有人看到。

---

## 关于本仓库

本仓库是闲沐 IMS 的**官方发布与反馈渠道**，用于提供安装包、更新说明与问题跟踪。

**闲沐 IMS 是闭源商业软件，源代码不公开。** 你可以免费下载、安装并使用免费版；本仓库不提供源码，也不接受源码相关的 Pull Request。这不是"开源项目"——请在依赖它之前确认这一点。

- 安装包 / 更新说明 / 历史版本：[Releases](../../releases)
- 软件许可与使用范围：[LICENSE](LICENSE)
- 安全问题与密钥泄露上报：[SECURITY.md](SECURITY.md)
- 官网与用户中心：[ims.miaoking.com](https://ims.miaoking.com) · [portal](https://ims.miaoking.com/portal/dashboard)

---

<div align="center">

**闲沐 IMS** · 极客AI · 物品管理

[官网](https://ims.miaoking.com) · [在线演示](https://imsdemo.miaoking.com) · [下载最新版](https://github.com/miaokingsoft/XianMuIMS/releases/latest/download/XianMuIMS-setup.exe) · [Releases](../../releases)

</div>
