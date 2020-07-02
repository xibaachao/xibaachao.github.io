---
categories: 
- 软件推荐
tags:
- 软件使用
---
#### hexo 安装

>环境配置
>
>git nodejs hexo 

#### 环境安装

- git安装（百度）

- nodejs安装（百度）

- hexo 安装

  >Node.js 版本需不低于 8.10，建议使用 Node.js 10.0 及以上版本
  >
  >npm install -g hexo-cli
  >
  >hexo init 项目名
  >
  >进入项目文件夹执行： npm install hexo-deployer-git --save
  >
  >进入项目文件夹 hexo server 启动项目
  >
  >或者使用yarn
  >
  >yarn global add hexo

#### hexo使用

>https://hexo.io/zh-cn/ 推荐多看看官方文档 

- github 

  登录github 创建一个新项目

  获取git地址!如：https://github.com/xibaachao/xibaachao.github.io.git

- 主题更换

  > https://hexo.io/themes/ 下载一个主题
  >
  > 将主题文件夹拷贝到根目录下的/themes下
  >
  > 配置主题：打开根目录下的_config.yml 编辑theme：主题文件夹
  >
  > 编辑文章：在source\\\_posts 发布文章，一个.md 就是一篇文章
  >
  > 配置github：打开根目录下的_config.yml 编辑deploy
  >
  > deploy:
  >
  >  type: git
  >
  >  repo: https://github.com/xibaachao/xibaachao.github.io.git
  >
  >  branch: master
  >
  > 

- hexo生成发布

  ```php
  hexo server //启动本地服务器
  hexo clean//为清除缓存
  hexo g //为生成本地文件夹
  hexo d //为发布到github page上
  ```

#### 配置本地发布环境

进入项目文件夹

```php
git init
git checkout -b make
git add --all
git commit -m "第一次提交"
git remote add origin https://github.com/xibaachao/xibaachao.github.io.git
git push origin make
```

注：此操作是，把hexo发布工具上传到git 并创建了一个叫make的分支





