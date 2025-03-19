# AI2Apps-user-manual  

[English](./README.md) 

## 🚀 快速开始
AI2Apps可以直接在网页中使用，也可以用本项目部署在本地使用。

### 1. 直接使用网页版

- 用桌面浏览器访问： [https://www.ai2apps.com](https://www.ai2apps.com)  

<div style="color:gray; text-indent:30px;">
    <div>第一次打开网页会进行开发环境安装与配置，根据浏览器以及网络的不同，大概需要几秒到1分钟的时间。</div>
    <div>测试期间，要访问 AI 模型，需要注册并登录 Tab-OS（注册 Tab-OS 账号完全免费）。成功注册/登录后，就可以使用项目向导就创建 AI Agent 项目了。</div>
</div>


### 2. 部署本地环境

- 安装 [Anaconda](https://www.anaconda.com/) 

- 下载 [AI2Apps Demo](https://github.com/Avdpro/ai2apps)

```bash
git clone https://github.com/Avdpro/ai2apps.git
```

- 修改.env文件，配置正确的OpenAI Key以及服务端口，默认的端口是3015。

```
APIROOT=https://www.ai2apps.com/ws/
OPENAI_API_KEY=sk-XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
PORT=3015

# 注释解除
AAF_EXECUATABLE=/Applications/Google Chrome.app/Contents/MacOS/Google Chrome
```

- 安装依赖

```bash
cd ai2apps
nmp install
```

```bash
cd agents
pip install -r requirements.txt
```

- 启动项目

```bash
cd ai2apps
node ./start.js
```

<p style="color:gray;">当ai2apps项目启动成功后，浏览器将自动打开dashboard页面。</p>

<p align="center">
  <img src="./assets/aa_home_cn.jpg" alt="home" />
  <span style="color:gray;font-size:12px;">dashboard.jpg</span>
</p>

## 👋 入门指南

- [简单对话](./doc/simple-chat-zh_CN.md)
- [创建项目](./doc/create_project-zh_CN.md)



































