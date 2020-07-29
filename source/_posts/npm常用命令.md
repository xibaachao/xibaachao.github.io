---
categories: 
- 编程开发
tags:
- 前端

---

​	``npm install -g cnpm --registry=https://registry.npm.taobao.org``

<!--more-->

#### 常用命令

- npm install xxx  安装 
- npm install xxx -g 全局安装
- npm install xxx -save  安装并写入package.json的”dependencies”中 就是写入到生存环境中
- npm install xxx –save-dev 安装并写入package.json的”devDependencies”中 写入到开发环境中
- npm uninstall xxx 删除xxx依赖
- npm uninstall xxx -g 删除全局依赖

- npm cache clean 清除缓存

#### 关于dependencies与devDependencies

- `dependencies` 表示我们要在**生产环境**下使用该依赖
- `devDependencies` 则表示我们仅在**开发环境**使用该依赖。