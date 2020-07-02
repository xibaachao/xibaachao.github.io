---
categories: 
- 编程开发
tags:
- PHP

---

#### thinkphp5.0 配置扩展独立的配置文件

在```config/app.php```中配置

```php
'extra_config_list'=> ['data']
```

配置完成后你就可以在config文件夹下建立data.php

```php
return [
    // 类型
    'type'        => ['xxx','xxx'],
 ];
```



到此你就在你的代码中调用```$type=config("type");```或者```Config::get('data.type');```

以上网络找的解决方案

#### thinkphp5.1 独立配置文件读取

在config/下建立一个php文件，如data.php

```php
<?php
return [
    "peopletype"=>['专家','人才']
];
```

如何读取！

````php
{~$temp=config("data.peopletype")} //视图中读取
$temp=config("data.peopletype");//控制器读取
````

