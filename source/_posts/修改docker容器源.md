---
categories: 
- 编程开发
tags:
- 服务器
---

#### 修改docker内部源

```bash
//进入容器后
sed -i "s@http://deb.debian.org@http://mirrors.aliyun.com@g" /etc/apt/sources.list && rm -Rf /var/lib/apt/lists/* &&  cat /etc/apt/sources.list
```

