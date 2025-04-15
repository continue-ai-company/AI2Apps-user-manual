<a name="readme-top"></a>

#### 发布周期

- 新增功能
- 调整、优化功能
- 日常 bugfix 更新

## 变更记录
`2025-04-15`
- 支持 OpenAI 的 `ChatGPT 4.1/4.1-mini/4.1`。
- 支持 `Claude 3.7`，支持了 Claude 的 Image-Input。
- 优化了 Agent 文件的 SaveAs，在 SaveAs 的时候，会自动改名以及修改 `jaxId`。
- 优化 UI ：输出的超长文本强制换行，Menu 菜单文本支持换行。
- `FixArgs` 组件支持了向上询问机制。
- 编写了专门用来回答向上询问的智能体：`SysReplyTool/SysTabOSReplyTool`。

`2025-04-08`
- Agent 层级对话机制。
- ApiProxy：辅助 AI 编程应对 Yahoo 财经之类的需要 API-Key 的机制。
- `Loop` 支持异步循环，更新了 RpaWebSearch 作为使用参考。

`2025-03-31`
- 保存 HubFile 的时候，如果文件名包含特殊字符，会简化文件名。
- Dashboard 和其对话初步支持了 `AI-Model` 设置。
- 新增功能：AA 服务器支持 `RAG`。
- 优化了编写单 HTML 的 Agent，支持续写等。
- 一些 bugfix。

`2025-03-28`
- 修复网页端和后端 Agent 语言不统一的问题。
- 调整 `SysTabOSChat`，只有输入以`/`开头，才进行命令检测。
- 新增网页端 Sandbox，可以用来执行编写的网页。
- 新增可编写简单网页的Agent，支持多轮对话完善网页，支持在对话时添加截图提高与 AI 的沟通效率。
- 一些 bugfix。

`2025-03-22`
- 新增ChatEntry机制，在Dashboard页面，可以选择默认对话的工具/入口。
- 优化默认对话Agent对附件的处理方式，确保附件可以正确的传递给Agent。详细的Agent读取附件，可参考AgentBuilder/ai/SysReadImage.js智能体。
- 调整`智能体市场`、`当前时间`、`RpaWebSearch`、`SysReadImage`智能体为系统智能体。

`2025-03-21`
- 修复从工具市场安装时，同步目录的bug

`2025-03-20`
- 优化`聊天输入`组件，新增`允许文件`属性。
- 合并`aarpa`库至`aae`库。

`2025-03-14`
- 新增目录比较、文件比较以及合并工具。
- 调整 `TabEdit` 和 `EditKit` 的打包方式。
- 优化了 `WebRPA` ，新增了`关闭浏览器`组件。
- 在 `WebRPA` 中，新增了在启动浏览器时，可以控制浏览器位置的功能，需要写几行代码，具体可参 `AgentBuilder/RpaWebSearch.js` 文件。
- 在 AI2Apps 首页，新增添加 Agent 功能，支持直接选择文件添加后端的 Agent 。

`2025-03-03`
- 新增在`飞线`组件选中时，可以看到跳转的目标组件。
- `项目向导`中，新增了语音项目和绘图项目的部署模板。
- `项目向导`中，新增了用于测试项目部署的专门模版。
- 新增了在 `Ubuntu` 上部署 `AI2Apps` 的支持（仍在测试阶段）。
- 一些 bugfix 。

`2025-02-20`
- 修复`管理帐户`无法打开的问题。
- 优化本地部署的 AI2Apps 启动流程。启动后，系统将自动打开 `Dashboard` 页面。
- 在 AI2Apps 的 `DashBoard` 页面对话功能中，引入新的 `SysTabOSChat` 智能体。
- 优化 `SysTabOSChat` 智能体对话，支持用户直接输入 `TabOS` 命令。

`2025-02-18`
- 新增 `WebRPA` 等待组件的异常处理，包含处理 Timeout 。
- 新增自动检测 `Conda` 路径的功能，无需用户手动填写。

`2025-02-17`
- 创建新项目更改为使用 AgentBuilder 智能体。
- 创建新的后端项目（Node.js/Python）时，使用 `setup.js` 自动同步到后端。
- 支持后端项目的安装和配置机制
  - 使用 `setup_agent.js` 通过脚本配置部署：Python 绘图。
  - 使用 `setup_guide.md` 通过 AgentBuilder 根据指南部署：Python 语音。
- IDE 启动调试时，自动检测工程是否需要和后端同步；如果需要同步，提示用户，用户可以立刻选择同步再调试。
- IDE 启动调试 Agent 时，增加了 `SlowMo` 和 `StepRun` 选项，可以让调试 Agent 一启动就进入慢动作或者单步执行状态。
- 一些 bugfix 。

`2024-12-16`
- 新增了微信对接。

`2024-11-13`
- 优化了 Agent 启动后的报错信息显示。

`2024-06-20`
- 支持 Web Agent 通过 `Zero-shot` 方式学会控制网页
- 支持 Web Agent 通过 `Zero-shot` 方式学会控制网页
- 支持用户构建可自适应适配目标网页的 Web Agent + RPA 。

`2024-06-15`
- 支持 Agent/组件 的全自动、半自动开发机制。无需编程，用户可通过与 Agent 语言交互来构建新 Agent/组件。
- 支持 Agent/组件 的发布和发现，用户之间可自由共享 Agent/组件。

`2024-05-25`
- 新增功能：用户可以通过内置的浏览器控制组件来构建 Web Agent 。
- 支持用户通过 `Ollama` 调用本地计算机上的大型语言模型。
- 支持用户将已有 Agent 作为 API 或组件使用。
 
<p align="right" >
  <a href="#readme-top">
    ↑ 返回顶部 ↑
  </a>&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="./README-zh_CN.md">
    🔗 返回主页
  </a>
</p>
