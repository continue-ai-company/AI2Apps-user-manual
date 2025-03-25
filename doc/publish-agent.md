## Publish Agent

### Confirm the Output Information

- Please make sure your project works correctly.

- **App**: The entry of App must be a `.html` file. If your project is going to register App, please make sure you have the correct html file entry.

- **Agent**: If your project is going to register Agent, please open the option `Export as Add on` in AI Agent `object properties`.

<div><img src="../assets/publish_agent9.jpg" alt="publish_agent9" /></div>

### Install Script 

#### setup.js

- When installing App or Agent, it will read the `./setup.js` file in your project and call the default output function from this file, then you can get the installation step and execute the installation script.

- Usually, the App and Agent running on the front end do not need to write `./setup.js` file. If project. If the project content needs some additional logic or operations to be performed after being deployed in Tab-OS, it can be written in the `./setup.js` file.

- If the Agent runs on the back end, you should add the step of sync files in the `./setup.js` file.

- If the back end Agent needs to perform the deployment process, you should add the AI agent that can call the deployment project in the `./setup.js` file.

-  The `./setup.js` template of the back end Agent is as follows:

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
		"syncDir":{
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

#### Back-end Deployment Scripts

If your back end Agent installation requires further deployment, such as initializing the conda environment, installing brew/npm/pip dependencies, downloading hf models and more, the `./setup_agent.js` or `setup_guide.md` file must be in the directory of the back end Agent. This is used to guide the project deployment. 

For details about the deployment, please see [deployment guide]().

### 填写 disk.json

