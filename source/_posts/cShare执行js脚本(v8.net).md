---
categories: 
- 编程开发
tags:
- C#
---
- 下载安装v8.net插件

![](/images/2020/6.png)

- 后台`c#`代码

```c#
var v8 = new V8Engine();
//初始化
string js = File.ReadAllText("xxx.min.js");
//加载某个js插件
Handle result = v8.Execute(js);
//返回执行js完成后的值
MessageBox.Show(result.ToString());

```

- `js`代码

```js
function temp(){
    return "xxxxx";
}
temp();
```

