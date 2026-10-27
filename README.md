# 启奏 · Ensemble

**在 Codex 中管理你的 AI 团队。**

Windows 试用版 / macOS 实验版 · 当前版本 **v2.3.23**

[下载 Windows 安装包](https://github.com/boxInAi/ensemble-codex/releases/download/v2.3.23/qizou-2.3.23-windows.zip) · [发布说明](https://github.com/boxInAi/ensemble-codex/releases/tag/v2.3.23) · [反馈问题](https://github.com/boxInAi/ensemble-codex/issues)

[下载 macOS 实验版](https://github.com/boxInAi/ensemble-codex/releases/download/v2.3.23/qizou-2.3.23-macos.zip)

Mac 版已完成适配和自动化检查，**尚未真实 Mac 实机验收，未经过 Apple 签名与公证**。适配 Apple 芯片和 Intel；完整解压后双击 `Install.command`，自动准备私有 Node.js 与图片组件，无需 Homebrew 或 Python。先安装并登录 Codex（或含 Codex 的 ChatGPT 桌面版）。安装器最低 macOS 13.5，宿主应用要求如更高，以其要求为准。

v2.3.23 已修复隐藏页面继续轮询、通信请求堆积及旧后台未能切换的问题。普通断线会自动重连；宿主渲染器完全崩溃时，需关闭该工作区后重新打开。该修复不等于已证明宿主崩溃的根因。

## 能做什么

- 用头像和成员列表进入各自的 Codex 聊天，保留原聊天记录。
- 新增、修改、移除成员，自定义名称、职责和头像。
- 默认提供 **18 张宠物头像**；上传头像作为独立文件保存在本机。
- 支持图片选择、粘贴和拖入，以及可用模型、推理强度和权限选择。大图分块上传，预览缩略图，发送时保留原图。
- 草稿与附件保存在本机，刷新可恢复；图片读取失败可单独重试。
- 显示聊天摘要和工作状态，支持原聊天与插件之间的写入权交接。

成员拥有独立聊天。跨成员协作需要明确分配任务；当前版本不提供项目群聊、@多成员自动调度或完整文件预览器。部分模型与权限设置受原聊天持有状态限制。

## Windows 安装

1. 在 **64 位 Windows** 上安装并登录 Codex，至少打开一次。
2. 下载上方的 **`qizou-2.3.23-windows.zip`**，完整解压。不要下载 GitHub 自动生成的 `Source code` 压缩包安装。
3. **双击 `Install.cmd`**，等待窗口显示“安装和运行检查全部通过”。不用打开终端、粘贴代码或使用管理员账户。
4. **完全退出后重新打开 Codex**，在左侧 **“…” → 启奏** 打开工作区，或在插件详情点击 **打开启奏工作区**。入口可自行固定到侧栏。第一次点击 **创建我的团队**，会在你的账户建立 **统筹 + 12 位工程师，共 13 个独立聊天**。初始化不会发送模型消息；之后可自行增删成员。

安装器自动启动 `Install.ps1`，检测并定位 Codex、Node.js 和 Python/Pillow。缺少运行环境时，会从官方站点下载经过 SHA-256 校验的插件专用组件，因此首次安装需要联网。不会永久修改 PowerShell 执行策略、系统 PATH 或系统 Python/Node.js；如果组织组策略禁止 PowerShell，仍需要管理员处理。

插件文件会复制到 `%LOCALAPPDATA%\OpenAI\Ensemble\packages\`。注册前检查页面、18 张头像、图片解码和聊天服务；注册后再通过 Codex 实际检查 MCP 加载、全局入口和页面读取；失败会保留原因和日志，不会显示安装成功。日志在 `%LOCALAPPDATA%\OpenAI\Ensemble\logs\`。

这是供安装试用的发行仓库，插件运行文件包含在 Release 安装包中；尚未上架官方公共插件目录。

## 数据保存在你自己的电脑

- Windows 默认目录：`%LOCALAPPDATA%\OpenAI\EngineeringTeam`；Mac：`~/Library/Application Support/OpenAI/EngineeringTeam/`。
- 新安装带有 13 位成员模板和 18 张默认头像，**不包含作者的聊天、成员自定义资料、账户凭据或上传图片**。
- 头像和消息图片存放在独立静态资源文件夹中，不内嵌到页面。
- 同名插件升级保留本机成员、头像与聊天映射。删除面板成员不会删除 Codex 原聊天。

请勿将自己的用户数据目录提交到仓库或反馈附件。

## 试用与反馈

目前已验收 Windows 本地安装流程；macOS 发布实验版但尚未实机验收，Linux 尚未验收。欢迎通过 Issues 提交：版本号、Windows/Codex 版本、复现步骤、预期行为和实际行为。分享截图前请遮盖私人聊天、文件路径和账户信息。

安装包附有更详细的静态资源与升级说明。Release 同时提供 SHA-256 校验文件。
