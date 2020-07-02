---
categories: 
- 编程开发
tags:
- 前端开发 
---
在工作我们经常会用验证码来预防别人恶意提交，所以点击更新验证码和刷新验证码是比较常用的。

而以下代码就是我们常用的**点击更换验证码**

```
<img border="0" src="xxxx" id="validator" οnclick="this.src='xxx?id='+Math.random();" title="看不清可单击图片刷新">
```

