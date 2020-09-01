---
categories: 
- 编程开发
tags:
- GO

---

go 使用中国源 

<!--more-->

### 配置环境：

```bash
go env -w GO111MODULE=on
启用 Go Modules 功能
go env -w  GOPROXY=https://goproxy.cn,direct 
七牛 CDN
go env -w GOPROXY=https://mirrors.aliyun.com/goproxy/,direct
阿里 CDN
go env -w  GOPROXY=https://goproxy.io,direct
官方 CDN
```

### 注意！

开启go modules 后

需要在项目中使用 `go mod init` 初始化不然要报错！！！！