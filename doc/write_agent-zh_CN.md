## 📝 编写 Agent 


## 如何编写 Agent
在AI2Apps中，每个 Agent 是一个独立的js文件，拓扑图信息以注释的形式保存在文件末尾，
从而保证了设计与实现随时同步。  
Agent文件编辑界面有"代码"和"画布"两种模式，打开 Agent 后默认进入画布模式。

#### 画布模式
开发 IDE 在画布模式下：  
  
<p align="center">
  <img src="assets/aaide_01_cn.png" alt="home" width="700" />
</p>


左侧是 Agent 的组织结构视图，这里显示 Agent 对象以及其包含的"执行片段"对象列表，点击项目可以选中对象。 
中间是 Agent 拓扑图画布，在这里可以通过拖拽创建"执行片段"对象，并通过拖拽把片段之间连接起来。  
右侧是对象属性编辑器视图，在这里会列出当前选中的对象的可编辑属性，例如调用 ChatGPT 时的模型选择、温度参数等。
 
#### 代码模式
开发 IDE 在代码模式下：  
  
<p align="center">
  <img src="assets/aaide_02_cn.png" alt="home" width="700" />
</p>

左、右侧不变，依然是 Agent 的组织结构与对象属性编辑视图，中间部分则是 Agent 代码，
编辑 Agent 拓扑图以及对象属性时，代码会自动更新，开发者也可以自己手动编写代码实现可视化编辑无法完成的逻辑。

#### 运行 Agent

<p align="center">
  <img src="assets/aa_run_cn.png" alt="home" width="700" />
</p>
运行按钮在 IDE 左侧的组织结构栏和 IDE 底部的综合工具栏中。点击运行按钮即可以调试模式或者终端模式运行当前的 Agent 项目。
Agent 启动后，你可以通过对话测试 Agent。

#### 调试 Agent
 
<p align="center">
  <img src="assets/aa_debug_cn.png" alt="home" width="700" />
</p>
以 Debug 模式启动 AI Agent 即进入调试模式。在调试模式中，点击 UI 顶部的"Debug"按钮就可以进入调试视图。  
**信息流及断点**   
调试视图左侧是信息流，在这里可以查看详细的对话流程，每一步进/出的内容。点击流程中步骤的的名字可以在右侧打开步骤的详细记录，并可以设置断点。  

**单步执行与断点操作** 
在 UI 底部可以打开单步执行功能，在单步执行 AI Agent 时或遇到断点时，调试器会暂停执行并向用户汇报当前步骤的执行信息，用户可以修改步骤的输入/输出信息查看不同的效果。  

**GPT Cheat**
在调试时可以使用GPT Cheat，点击调用 GPT 的步骤，可以在右侧的面板中添加 GPT Cheat。通过 GPT Cheat 可以用预先设置好的结果模拟（绕过）ChatGPT 调用，从而节省时间与成本。

**拓扑图追踪调试信息**

<p align="center">
  <img src="assets/aa_trace_cn.png" alt="home" width="700" />
</p>

在调试 AI Agent 的过程中，Agent 的拓扑图会同步更新，标注执行调用的路径及各种参数传递的过程。
执行经过的路径会用加粗的蓝色曲线高亮显示，执行的输入输出则会在对象属性视图的**Trace Log**中列出。

### 能量及消耗
如果使用自己部署的AI2Apps环境并配置了 OpenAI Key，调用 ChatGPT 将使用开发者本人的 OpenAI 流量。
这种情况下系统不会有任何限制。   
如果使用的是www.ai2apps.com环境运行/调试 Agent，在执行ChatGPT调用时会产生由系统承担的 OpenAI 费用。
为了避免账单崩溃，系统通过"能量"限制用户对ChatGPT的调用量。  

### 获得能量
在成功注册登录 Tab-OS 后，用户会获得一定的免费能量，
每天登录后也会根据当前用户等级为用户补充一定的能量。推荐新成员用户成功也可以获得免费的系统代币，
可用于兑换能量。

### 发布 Agent
编辑好的 Agent 可以打包发布为网页或移动应用（iOS/安卓）。 


<p align="right" >
  <a href="../README-zh_CN.md">
    🔗 返回主页
  </a>
</p>