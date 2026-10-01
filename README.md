<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://ims.miaoking.com/github/logo-horizontal-dark.png">
  <img src="https://ims.miaoking.com/github/logo-horizontal.png" alt="闲沐 IMS · AI 智能物资管理平台" width="360">
</picture>

### 闲沐 IMS · 让 AI 记住你拥有的每一件东西。

**从"我记得我有"到"我知道它在哪"** · 从家里的收纳箱，到工作室的元件，再到实验室的设备和小仓库的库存。拍照、扫码、定位、搜索、管理，让现实世界的物品拥有自己的数字档案。

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

---


<div align="center">

**闲沐 IMS** · 极客AI · 物品管理

[官网](https://ims.miaoking.com) · [在线演示](https://imsdemo.miaoking.com) · [下载最新版](https://github.com/miaokingsoft/XianMuIMS/releases/latest/download/XianMuIMS-setup.exe) · [Releases](../../releases)

</div>
