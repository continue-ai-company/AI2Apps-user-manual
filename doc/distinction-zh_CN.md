# 如何调试JS版项目？

## 1. 显示详细的Object内容

1. 选中单个block，在页面右侧会显示 `对象属性` 面板；

2. 在 `输出内容` 一栏，添加以下代码，即可显示详细的Object内容；
```
#`
    \`\`\`
        ${JSON.stringify(input,null,"\t")}
    \`\`\`
`  
```

3. 若想获取Object内容中单个key的值，则添加以下代码：
```
#`${JSON.parse(JSON.stringify(input,null,"\t"))['keyword']}`
```

## 2. 设置并获取上下文

### 2.1 设置上下文

1. 点击页面左侧 **AI智能体**，在页面右侧会显示 `对象属性` 面板；

2. 找到 `上下文` 区域，点击旁边的 **加号**；

3. 在页面顶部的弹出层中，填写 `变量名`， 点击 **确定** 按钮；

4. 在`对象属性`面板中，点击 `变量名`，填写 `数据类型` 等。

### 2.2 获取上下文的值

```
context.VariableName
```

## 3. LLM系统设定的格式

```
#`文字描述${context.VariableName}`
```


# 如何调试Python版项目？

## 1. 显示详细的Object内容

1. 选中单个block，在页面右侧会显示 `对象属性` 面板；

2. 在 `输出内容` 一栏，添加以下代码，即可显示详细的Object内容；

```
#json.dumps(input, indent='\t', ensure_ascii=False)
```

## 2. 设置并获取上下文

### 2.1 设置上下文

1. 点击页面左侧 **AI智能体**，在页面右侧会显示 `对象属性` 面板；

2. 找到 `上下文` 区域，点击旁边的 **加号**；

3. 在页面顶部的弹出层中，填写 `变量名`， 点击 **确定** 按钮；

4. 在`对象属性`面板中，点击 `变量名`，填写 `数据类型` 等。

### 2.2 获取上下文的值

```
#写法一
context.get('VariableName')

#写法二
context['VariableName']
```

## 3. LLM系统设定的格式

```
#f'''
文字描述
{context.get('VariableName')}
数据结构：{{ title:'' }}
'''
```