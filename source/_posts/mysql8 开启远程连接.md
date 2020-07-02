---
categories: 
- 编程开发
tags:
- Mysql

---

#### 第一步

```sql
 mysql -u root -p ‘原来的密码’ 
```

#### 第二步

```
 use mysql;
```

#### 第三步

```mysql
CREATE USER 'root'@'%' IDENTIFIED BY '你的密码';
GRANT ALL ON *.* TO 'root'@'%';
ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY '你的密码';
```

#### 第四步

```
FLUSH PRIVILEGES;
```

