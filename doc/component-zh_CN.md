# 🧩 使用组件

## 常用

### 聊天输入 

作用：用户聊天输入。

#### 1. 基础操作

在组件工具栏中，鼠标左键点击`聊天输入`，右侧画布则会显示`聊天输入`组件。
<p>
    <img src="../assets/user-chat1_component_cn.jpg" alt="user-chat1" />
</p>

在焦点处输入组件名称，如 **UserInput**，再按下 `enter` 键，即可为组件命名。
<p>
    <img src="../assets/user-chat2_component_cn.jpg" alt="user-chat2" />
    <img src="../assets/user-chat3_component_cn.jpg" alt="user-chat3" />
</p>

鼠标右键点击组件，组件下方将显示菜单选项，分别为`选择右侧相关组件`、`删除组件`、`设置组件标记`。
<p>
    <img src="../assets/user-chat5_component_cn.jpg" alt="user-chat5" />
</p>

鼠标左键点击组件，右侧会显示相应的对象属性面板。
<p>
    <img src="../assets/user-chat4_component_cn.jpg" alt="user-chat4" />
</p>

#### 2. 对象属性详解

**ID 名称**：该组件的唯一标识，不可重复，建议用英文命名。

**显示名称**：该组件的展示名称。

**提示文本**：可用作提示用户输入的引导语。

<div><img src="../assets/user-chat6_component_cn.jpg" alt="user-chat6" /></div>
<div><img src="../assets/user-chat7_component_cn.jpg" alt="user-chat7" /></div>

**提示角色**：用于设置提示文本所相应的角色。
<div><img src="../assets/user-chat10_component_cn.jpg" alt="user-chat10" /></div>

**占位提示**：输入框内的默认提示内容。

<div><img src="../assets/user-chat8_component_cn.jpg" alt="user-chat8" /></div>
<div><img src="../assets/user-chat9_component_cn.jpg" alt="user-chat9" /></div>

**默认输入文本**：输入框内的默认的占位内容。

<div><img src="../assets/user-chat11_component_cn.jpg" alt="user-chat11" /></div>
<div><img src="../assets/user-chat12_component_cn.jpg" alt="user-chat12" /></div>

**在对话中显示**：用于设置输入框内容是否在对话过程中进行展示。假设用户输入内容为**这是测试数据**，选择`是`，则代表在对话过程中显示该输入内容，如下图所示；选择`否`，则代表不显示该输入内容。

<div><img src="../assets/user-chat13_component_cn.jpg" alt="user-chat13" /></div>
<div><img src="../assets/user-chat14_component_cn.jpg" alt="user-chat14" /></div>

**允许文件**：用户可设置是否上传附件。选择`是`，则代表用户在输入过程中可以上传附件；选择`否`，则只能输入文字，无法上传额外附件内容。

<div><img src="../assets/user-chat15_component_cn.jpg" alt="user-chat15" /></div>
<div><img src="../assets/user-chat16_component_cn.jpg" alt="user-chat16" /></div>
<div><img src="../assets/user-chat17_component_cn.jpg" alt="user-chat17" /></div>
<div><img src="../assets/user-chat18_component_cn.jpg" alt="user-chat18" /></div>

**询问上级 Agent**：选项值为`是`或`否`。

<div><img src="../assets/user-chat19_component_cn.jpg" alt="user-chat19" /></div>

**附有代码**：可在代码指定编辑区域内添加代码。选择`是`，则代表用户可以添加代码；选择`否`，则无法添加代码。

<div><img src="../assets/user-chat20_component_cn.jpg" alt="user-chat20" /></div>
<div><img src="../assets/user-chat21_component_cn.jpg" alt="user-chat21" /></div>
<div><img src="../assets/user-chat22_component_cn.jpg" alt="user-chat22" /></div>

**更新上下文**：用于设置变量名与变量值，可在其他组件中使用。点击右侧**加号**按钮，选择`数据类型`，填写`变量名`和`变量值`，即可进行上下文设置。另外，点击`变量映射`旁边的**箭头**图标，会显示上下文变量名列表，在变量名后面填写对应的值，即可完成上下文值的更新。该值可以来源于上一个组件或当前组件的输出，**input** 表示为当前组件的输入，也可以称之为上一个组件的输出，**result** 表示为当前组件的输出。当前设置也可以在代码编辑区域内进行查看或修改。

<div><img src="../assets/user-chat23_component_cn.jpg" alt="user-chat23" /></div>
<div><img src="../assets/user-chat24_component_cn.jpg" alt="user-chat24" /></div>
<div><img src="../assets/user-chat25_component_cn.jpg" alt="user-chat25" /></div>
<div><img src="../assets/user-chat26_component_cn.jpg" alt="user-chat26" /></div>
<div><img src="../assets/user-chat27_component_cn.jpg" alt="user-chat27" /></div>

**更新全局上下文**：用于设置全局使用的变量。使用方法请参考`更新上下文`。

**说明**：对该组件的辅助说明。

<div><img src="../assets/user-chat28_component_cn.jpg" alt="user-chat28" /></div>

**Trace logs**：当前组件运行的日志。

<div><img src="../assets/user-chat29_component_cn.jpg" alt="user-chat29" /></div>

### 调用LLM

作用：调用AI模型。

#### 1. 基础操作

请参考[ 聊天输入 ](#聊天输入)。

#### 2. 对象属性详解

**ID 名称**：该组件的唯一标识，不可重复，建议用英文命名。

**显示名称**：该组件的展示名称。

<!-- **输入（样板）**： -->

**AI 平台**：

<div><img src="../assets/call-llm1_component_cn.jpg" alt="call-llm1" /></div>

**AI 模型**：

<div><img src="../assets/call-llm2_component_cn.jpg" alt="call-llm2" /></div>

**调用参数**：用于设置模型参数。

<div><img src="../assets/call-llm3_component_cn.jpg" alt="call-llm3" /></div>

**系统设定**：用于编写提示语。

<div><img src="../assets/call-llm4_component_cn.jpg" alt="call-llm4" /></div>

**预置对话**：

<div><img src="../assets/call-llm6_component_cn.jpg" alt="call-llm6" /></div>

**提示（Prompt）**：可用作指定输出内容的格式。

**高级设置**：

<div><img src="../assets/call-llm5_component_cn.jpg" alt="call-llm5" /></div>

**附有代码**：可在代码指定编辑区域内添加代码。选择`是`，则代表用户可以添加代码；选择`否`，则无法添加代码。

**说明**：对该组件的辅助说明。

**Trace logs**：当前组件运行的日志。

### 文本输出

作用：显示结果或用作提示语展示。

#### 1. 基础操作

请参考[ 聊天输入 ](#聊天输入)。

#### 2. 对象属性详解

**ID 名称**：该组件的唯一标识，不可重复，建议用英文命名。

**显示名称**：该组件的展示名称。

<!-- **输入（样板）**： -->

**角色**：用于设置文本所相应的角色。

**输出内容**：当前组件对外显示的内容。

**附有代码**：可在代码指定编辑区域内添加代码。选择`是`，则代表用户可以添加代码；选择`否`，则无法添加代码。

**更新上下文**：用于设置变量名与变量值，可在其他组件中使用。点击右侧**加号**按钮，选择`数据类型`，填写`变量名`和`变量值`，即可进行上下文设置。另外，点击`变量映射`旁边的**箭头**图标，会显示上下文变量名列表，在变量名后面填写对应的值，即可完成上下文值的更新。该值可以来源于上一个组件或当前组件的输出，**input** 表示为当前组件的输入，也可以称之为上一个组件的输出，**result** 表示为当前组件的输出。当前设置也可以在代码编辑区域内进行查看或修改。

**更新全局上下文**：用于设置全局使用的变量。使用方法请参考`更新上下文`。

**说明**：对该组件的辅助说明。

**Trace logs**：当前组件运行的日志。

### 按钮询问

作用：方便用户不同操作选择。

#### 1. 基础操作

在组件工具栏中，鼠标左键点击`按钮询问`，右侧画布则会显示`按钮询问`组件。
在焦点处输入组件名称，如 **Btn**，再按下 `enter` 键，即可为组件命名。
<p>
    <img src="../assets/query-confirm2_component_cn.jpg" alt="query-confirm2" />
    <img src="../assets/query-confirm1_component_cn.jpg" alt="query-confirm1" />
    <img src="../assets/query-confirm3_component_cn.jpg" alt="query-confirm3" />
</p>

组件中最多可包含3个子按钮。选中其中一个，按下 `del` 键，点击`确定`即可进行删除。
<p>
    <img src="../assets/query-confirm4_component_cn.jpg" alt="query-confirm4" />
</p>

选中组件，组件右下角会显示一个**加号**按钮，点击该按钮即可添加新的子按钮。

<p>
    <img src="../assets/query-confirm5_component_cn.jpg" alt="query-confirm5" />
</p>

鼠标左键点击父组件、子按钮，右侧会显示相应的对象属性面板。

<p><img src="../assets/query-confirm6_component_cn.jpg" alt="query-confirm6" /></p>
<p><img src="../assets/query-confirm7_component_cn.jpg" alt="query-confirm7" /></p>

#### 2. 对象属性详解

##### 2.1 父组件对象属性：

**ID 名称**：该组件的唯一标识，不可重复，建议用英文命名。

**显示名称**：该组件的展示名称。

<!-- **输入（样板）**： -->

**提示文本**：可用作提示用户选择的引导语。
<p><img src="../assets/query-confirm11_component_cn.jpg" alt="query-confir11" /></p>

<!-- **Silent**：
<p><img src="../assets/query-confirm8_component_cn.jpg" alt="query-confir8" /></p>

**Silent outlet**：
<p><img src="../assets/query-confirm9_component_cn.jpg" alt="query-confir9" /></p> -->

**倒计时**：开启倒计时，在规定的时间内，按钮选项消失。
<p><img src="../assets/query-confirm10_component_cn.jpg" alt="query-confir10" /></p>

**附有代码**：可在代码指定编辑区域内添加代码。选择`是`，则代表用户可以添加代码；选择`否`，则无法添加代码。

**说明**：对该组件的辅助说明。

**Trace logs**：当前组件运行的日志。

##### 2.2 子按钮对象属性：

**ID 名称**：该组件的唯一标识，不可重复，建议用英文命名。

**文本**：该组件的展示名称。

**输出**：用于组件最终的输出结果。

<!-- **图标**：

**表情符号**： -->

**使用代码**：可在代码指定编辑区域内添加代码。选择`是`，则代表用户可以添加代码；选择`否`，则无法添加代码。

**更新上下文**：用于设置变量名与变量值，可在其他组件中使用。点击右侧**加号**按钮，选择`数据类型`，填写`变量名`和`变量值`，即可进行上下文设置。另外，点击`变量映射`旁边的**箭头**图标，会显示上下文变量名列表，在变量名后面填写对应的值，即可完成上下文值的更新。该值可以来源于上一个组件或当前组件的输出，**input** 表示为当前组件的输入，也可以称之为上一个组件的输出，**result** 表示为当前组件的输出。当前设置也可以在代码编辑区域内进行查看或修改。

**更新全局上下文**：用于设置全局使用的变量。使用方法请参考`更新上下文`。

**说明**：对该组件的辅助说明。

### 连接器

作用：组件与组件间的连接。

#### 1. 基础操作

在组件工具栏中，鼠标左键点击`连接器`，右侧画布则会显示`连接器`组件。
<p>
    <img src="../assets/connector1_component_cn.jpg" alt="connector1" />
    <img src="../assets/connector3_component_cn.jpg" alt="connector2" />
</p>

#### 2. 对象属性详解

<p>
    <img src="../assets/connector2_component_cn.jpg" alt="connector3" />
</p>

<!-- ### 条件分支

作用：用于不同条件判断。

#### 1. 基础操作

#### 2. 对象属性详解

### 代码片段
### 调用AI-Agent
### 注释 -->


<!-- 
branch
code seg
call ai agent
note -->



<p align="right" >
  <a href="../README-zh_CN.md">
    🔗 返回主页
  </a>
</p>



