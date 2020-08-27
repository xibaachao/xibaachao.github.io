---
categories: 
- 编程开发
tags:
- 前端开发
---

webpack 多模块开发 模板使用 公用模板使用

<!--more-->

### 安装html-loader

` npm install html-loader`

### 配置html-loader

- webpack.config.js

  ```  shell
   module: {
          rules: [{
          	test: /\.(tpl)$/,
                  use:{
                    loader: 'html-loader',
                    options: {
                      minimize: false
                    }
                  }
          }]
  ```

  > 注意！这里匹配的是.tpl的格式结尾的模板。

### 页面引入模板

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <%= require('./base/header.tpl') %>
</body>
</html>
```



