---
categories: 
- 编程开发
tags:
- PHP
---
#### laravel 访问器使用

在你的模型上，定义访问器，需要创建一个getXxxAttribute方法。需要访问的Xxxx为字段名，这里需要使用`大驼峰法命名法`（列如：name 需要命名为：Name ；my_name需要命名为：MyName）

列：

```php
<?php
namespace App\Models;
use Illuminate\Database\Eloquent\Model;
class Admin extends Model
{
    use Notifiable;
    protected $fillable = [
        'username', 'password','remember_token'
    ];
    protected $hidden = [
        'password','remember_token'
    ];
    //获取头像
    function getHeadimg($value){
        return config("url").$value;
    }
}
```

注：获取用户头像的时候，把url加上

#### laravel修改器使用

在你的模型上，定义访问器，需要创建一个setXxxAttribute方法。需要访问的Xxxx为字段名，这里需要使用`大驼峰法命名法`（列如：name 需要命名为：Name ；my_name需要命名为：MyName）

列：

```php
<?php
namespace App\Models;
use Illuminate\Database\Eloquent\Model;
class Admin extends Model
{
    use Notifiable;
    protected $fillable = [
        'username', 'password','remember_token'
    ];
    protected $hidden = [
        'password','remember_token'
    ];
    //登录密码加密
    function setpasswordAttribute($value)
    {
        $this->attributes['password']=encrypt($value);
    }
}
```

注：添加或者修改用户的时候，加密登录密码