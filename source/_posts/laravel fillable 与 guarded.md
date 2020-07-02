---
categories: 
- 编程开发
tags:
- PHP

---

#### fillable 与 guarded

> 官方解释 https://learnku.com/laravel/wikis/16126

#### fillable

```php
fillable 变量存储允许自动填充模型字段的数组，可以理解为字段修改 白名单，比如：
protected  $fillable = ['title', 'body', 'category_id'];
那么你就可以进行批量赋值
比如：
$post = Post::create($request->all()); //批量创建数据
```

#### guarded

```php
guarded 变量存储不允许自动填充模型字段的数组，可以理解为字段修改 黑名单，比如：
protected  $guarded=['user_id'];
$post = new Post($data);
$post->user_id = Auth::id();
$post->save();
```

