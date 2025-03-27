## 发布智能体

### 确认输出信息

- 请确认您的项目可以正确运行。

- **App**：App 的入口必须是 `.html` 文件。如果您的项目要注册 App 到 AI2Apps，确保您有正确的 html 文件入口。

- **智能体**：如果您的项目要注册 Agent 到 AI2Apps 系统，一定打开 Agent 的`输出组件`选项。

<div><img src="../assets/publish_agent9_cn.jpg" alt="publish_agent9" /></div>

### 安装脚本

#### setup.js

- 在安装 App 或 Agent 时，会读取项目下的 `./setup.js` 文件，调用这个文件的默认输出的函数，得到并执行安装步骤脚本。

- 通常 App 和在前端运行的 Agent 是无需编写 `./setup.js` 文件的。如果项目内容在 Tab-OS 里部署后还需要一些额外逻辑/操作要执行，可以写在 `./setup.js` 脚本里。

- 对于后端执行的 Agent，首先应该在 `./setup.js` 里增加同步文件的步骤。

- 如果后端的 Agent 需要执行部署过程，在 `./setup.js` 也要添加调用部署项目的 AI 智能体。

- 后端 Agent 的 `setup.js` 模版如下：

```js
import pathLib from "/@path";
let $ln="EN";
async function setupAgent(session,path,lan="EN"){
	let steps,dirName,nodeDirPath;
	$ln=lan;
	dirName=pathLib.basename(path);
	async function checkEnv(session){
		return true;
	}
	steps={
		"start":{
			"action":"Info",
			"description":"开始安装智能体项目",
			"next":(output)=>{return "ensurePackages"}
		},
		"ensurePackages":{
			"action":"Pkg",
			"packages":["AgentBuilder"],
			"description":(($ln==="CN")?("检查/安装项目依赖"):/*EN*/("Check/Install project dependencies")),
			"next":"syncDir",
		},
		"syncDir":{//同步文件到后端
			"action":"SyncDir",
			"dir":"ai",
			"target":dirName,
			"next":(result)=>{
				nodeDirPath=result.agentDir;
				if(nodeDirPath.startsWith("AGENTS/")){
					nodeDirPath=nodeDirPath.substring("AGENTS/".length);
				}
				steps["callStepUpAgent"].args={"prjPath":nodeDirPath};
				return "callStepUpAgent"
			}
		},
		"callStepUpAgent":{
			"action":"CallHubAgent",
			"agentNode":"AgentBuilder",
			"agent":"PrjSetupPrjByStep.js",
			"args":null,//Will be set on running...
			"next":null
		}
	};
	return steps;
}

```

#### 后端部署脚本 

如果你的后端 Agent 安装时需要进一步部署（例如初始化 conda 环境、安装 brew/npm/pip 依赖、下载 hf 模型等），需要在后端 Agent 的目录里有 `setup_agent.js` 或者 `setup_guide.md` 文件用于指导项目部署。具体请参考后端项目部署指南。

### 填写 disk.json

- 以下是计算器 App 的 `disk.json`：

```json
	{
		"imports": {
			"StdUI": "V1",
			"cokemake": "v1",
			"terser": "v1",
			"rollup": "v1"
		},
		"toolExport": [
			{
				"type": "Agent",
				"filePath": "./ai/execMath.js"
			},
			{
				"type": "App",
				"filePath": "./app.html",
				"name": {
					"EN": "Calculator",
					"CN": "计算器"
				},
				"description": {
					"EN": "Calculator App.",
					"CN": "计算器程序。"
				},
				"icon": "cal.svg",
				"package": "CalApp",
				"appFrameW": 400,
				"appFrameH": 600,
				"group": "Tools"
			}
		],
		"cloudId": "CalApp@avdpro@me.com",
		"versionIdx": 2,
		"version": "0.0.1"
	}
```

- **设置依赖**：在 Terminal 里当前的项目目录下，执行 `pkg import [package-name]` 来向`disk.json` 里添加当前工程的依赖项目。请确保项目依赖的非系统 package 在 `disk.json` 的import 对象里都已经声明了。

- **执行入口**：在 `disk.json` 的 toolExport 对象里添加 App/Agent 安装后向 AI2Apps 系统添加的 App/Agent 入口。

	- 不论是 App 还是 Agent，都必须有 `filePath` 属性，填入 App 或 Agent 的入口文件。在 AI2Apps 系统内入口文件的完整路径是区分不同 App/Agent 的唯一标识。
	
	- **APP**：如果是 App，需要详细填写详细的信息，包括名称、功能描述、图标、启动尺寸等。
	
	- **Agent智能体**：如果是 Agent，只需要提供入口 Agent 的 js 文件的相对路径即可。系统会读取文件的 `API输出` 信息。

- **图标**：图标如果是在 `/-tabos/shared/assets/` 目录下，可以直接使用文件名（例如："icon": "app.svg"）。如果图标是相对于当前项目等路径，请用`./`开头（例如："icon":"./icon/AppIcon.svg"）。

### 下载项目 zip 包

点击`文件管理器`，选中当前项目，点击 `Download folder as zip`，下载当前目录的 zip 包备用。

<img src="../assets/download_zip_cn.jpg" alt="download_zip" />

### 发布项目

- 点击侧边栏上的用户图标 -> 点击`管理帐户` -> 点击`发布新应用`。

<div><img src="../assets/publish_agent1_cn.jpg" alt="publish_agent1" /></div>
<div><img src="../assets/publish_agent2_cn.jpg" alt="publish_agent2" /></div>

- 输入`应用程序ID`（该内容代表发布项目的唯一标识，不是名称）-> 打开`发布到智能市场` -> 点击`下一步`。

<div><img src="../assets/publish_agent3_cn.jpg" alt="publish_agent3" /></div>

- 输入`应用程序名称` -> 选择`运行模式`。如果您有任何 Agent 运行在后端，请选择`后端智能体节点`，否则请选择`在 Tab-OS 里运行的应用或智能体`。

<div><img src="../assets/publish_agent5_cn.jpg" alt="publish_agent5" /></div>

- 填写您的应用或智能体`描述`。

<div><img src="../assets/publish_agent4_cn.jpg" alt="publish_agent4" /></div>

- 选择 App 或 Agent 的`图标`，该图标将在`智能体市场`显示。接着，选择之前下载的项目zip包作为`应用程序安装文件`。然后，输入`版本`，点击`下一步`。

<div><img src="../assets/publish_agent6_cn.jpg" alt="publish_agent6" /></div>

- 选择 App 或 Agent `分类`、`功能`，输入用于搜索的`标签`，再点击`发布`，即可将应用或智能体发布到`应用市场`。

<div><img src="../assets/publish_agent7_cn.jpg" alt="publish_agent7" /></div>

### 安装项目

详细步骤请参考[市场工具](./too_mart-zh_CN.md)。

### 升级智能体

升级智能体与发布智能体一样，需要先准备好智能体的 zip 包。点击侧边栏上的用户图标 -> 点击`管理帐户` -> 点击`我的应用` -> 选择要升级的 Agent 或 App -> 点击升级图标，更新智能体发布信息后，即可发布新版本。

> 注意：新的版本号要大于旧的版本号。

<div><img src="../assets/publish_agent8_cn.jpg" alt="publish_agent8" /></div>

<p align="right" >
  <a href="../README-zh_CN.md">
    🔗 返回主页
  </a>
</p>


