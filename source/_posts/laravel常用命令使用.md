---
categories: 
- 编程开发
tags:
- PHP

---

```php
php artisan make:model Models/Admin -m //创建model并创建表

php artisan make:controller Admin/DashboardController -r//创建controller

php artisan make:request AdminLoginRequest //生成一个request

php artisan make:seed AdminsTableSeeder //填充数据

php artisan migrate //创建表

php artisan db:seed //填充数据

php artisan db:seed --class=UsersTableSeeder //指定填充数据
  
php artisan make:middleware xxxx //创建中间件
```



