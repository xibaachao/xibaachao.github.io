---
categories: 
- 编程开发
tags:
- 前端开发
---
#### webpack 配置文件说明

webpack.config.js

#### 简易配置

```js
const path=require('path');
module.exports={
    entry:"",//入口文件
    output:{//输出文件
    	path:path.resolve(__dirname,"dist"),//指定目录
		filename:"xxxx.js",//文件名
	}
}
```

#### 多入口配置

```
const path=require('path');
module.exports={
    entry:{
    	home:"./home.js",
    	welcome:"./welcome.js"
    },
    output:{//输出文件
    	path:path.resolve(__dirname,"dist"),//指定目录
		filename:"[name].js",//文件名
	}
}
```



