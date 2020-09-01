---
categories: 
- 编程开发
tags:
- Mysql

---

mysql 生成数据库字典 sql语句

<!--more-->

```sql
SELECT
    t.TABLE_SCHEMA AS 库名,
    t.TABLE_NAME AS 表名,
    t.COLUMN_NAME AS 字段名,
    t.COLUMN_TYPE AS 数据类型,
    CASE IFNULL(t.COLUMN_DEFAULT,'Null') 
        WHEN '' THEN '空字符串' 
        WHEN 'Null' THEN 'NULL' 
        ELSE t.COLUMN_DEFAULT END  AS 默认值,
    CASE t.IS_NULLABLE WHEN 'YES' THEN '是' ELSE '否' END AS 是否允许为空,
    t.COLUMN_COMMENT AS 字段说明
FROM information_schema.COLUMNS t 
WHERE t.TABLE_SCHEMA='数据库名' AND t.TABLE_NAME='表名';
```

