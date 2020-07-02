---
categories: 
- 编程开发
tags:
- PHP

---

#### laravel 用户认证 多用户认证

- 创建表

```php
//php artisan make:migration create_User_table
Schema::create('users', function (Blueprint $table) {
	$table->bigIncrements('id')->comment("编号");
	$table->string("name")->comment("姓名");
	$table->string("password")->comment("密码");
	$table->string("phone")->comment("电话号码");
	$table->integer("pid")->comment("对应职务id");
	$table->integer("aid")->comment("负责区域id");
	$table->rememberToken();
	$table->timestamps();
});
//php artisan migrate
```

- 填充数据

```php
//php artisan make:seed UserTableSeeder 
 User::insert([
      "name"=>"钟建超",
      "password"=>bcrypt("123"),
      "phone"=>"123",
      "pid"=>1,
      "aid"=>1
]);
//php artisan db:seed
```



