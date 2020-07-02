---
categories: 
- 编程开发
tags:
- Mysql

---

#### phpmyadmin登录时指定服务器ip和端口的方法

- 在phpmyadmin 目录

> libraries/config.default.php

- 将```$cfg['AllowArbitraryServer']=false ```修改成```$cfg['AllowArbitraryServer']=true ```