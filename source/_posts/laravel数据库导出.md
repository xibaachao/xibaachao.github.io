---
categories: 
- 编程开发
tags:
- PHP
---

#### 安装扩展 orangehill/iseed

```php
composer require orangehill/iseed
```

#### 把iseed加入到服务提供者

在laravel项目目录 config/app.php 添加providers

```php
'providers' => [
    ...
    Orangehill\Iseed\IseedServiceProvider::class,
],
```

#### 导出单表

```php
php artisan iseed 表名
```

#### 导出多表

```php
php artisan iseed 表1,表2
```

#### 导出数据并且强制覆盖

```php
php artisan iseed 表名1,表名2 --force
```

#### 导出其他数据库的数据

```php
php artisan iseed 表名--database=数据库名
```



