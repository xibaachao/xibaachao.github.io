---
categories: 
- 编程开发
tags:
- PHP

---

Laravel分页视图带参数

做列表筛选的时候，时常会遇到带参数分页的情况



<!--more-->

在是视图中的代码

```php
{{$list->appends(['type'=>$type])->links()}}
```

在调用`links`方法前先调用`appends`来设置需要的参数

生成后代码会是：

```html
/xxx?type=xxx&page=1
```

