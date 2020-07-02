---
categories: 
- 编程开发
tags:
- PHP

---

#### 创建表

```php
php artisan make:migration create_表名_table
```

#### 建表语句

```php
    public function up()
    {
        Schema::create('user', function (Blueprint $table) {
            $table->bigIncrements('id')->comment("编号");
            $table->string("name")->comment("姓名");
            $table->string("password")->comment("密码");
            $table->string("phone")->comment("电话号码");
            $table->integer("pid")->comment("对应职务id");
            $table->integer("aid")->comment("负责区域id");
            $table->timestamps();
        });
        Illuminate\Support\Facades\DB::statement("ALTER TABLE `user` comment '用户表'");
    }
```

> 从上面的语句就可以看出表结构的语法，当然这里只是简单的写了一个表
>
> 具体可以查看laravel的数据库迁移文档
>
> https://learnku.com/docs/laravel/6.x/migrations/5173



