---
categories: 
- 编程开发
tags:
- Mysql
---

```sql
登录到mysql数据库
use mysql;
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'root' WITH GRANT OPTION;
flush privileges;
```

