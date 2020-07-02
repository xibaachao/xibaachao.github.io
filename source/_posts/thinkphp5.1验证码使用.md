---
categories: 
- 编程开发
tags:
- PHP
---
#### 安装插件

```
composer require topthink/think-captcha //thinkphp5.0
composer require topthink/think-captcha=2.0.* //thinkphp5.1
```



#### 生成验证码

```
use think\captcha\Captcha;//引入包
public function verify()
    {
        $captcha = new Captcha();
        $captcha->fontSize = 30;
        $captcha->length   = 4;
        $captcha->useNoise = false;
        return $captcha->entry("captcha");//生成验证码，并打个标签
}
```

#### 前端展示

```
<img src="{:url('admin/tool/verify')}" onclick="this.src=this.src+'&'+Math.random()" width="120" height="40" >
```

#### 后端检查

```
$captcha = new Captcha();
 if(!$captcha->check(input("vercode"),"captcha"))
 {
 	 return ["code"=>-1,"msg"=>"验证码错误"];
 }
```

注：
input("vercode");//用户输入的验证码
captcha；//为什么生成验证码时候打的标签



#### 更多看官方

[thinkphp5.1](https://www.kancloud.cn/manual/thinkphp5_1/354122)

[thinkphp5.0](https://www.kancloud.cn/manual/thinkphp5/154295)

