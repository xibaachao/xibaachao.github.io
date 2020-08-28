---
categories: 
- 编程开发
tags:
- PHP

---

laravel 自定义分页返回数据

在给前端返回数据的时候常常会用到分页，但是laravel 本身的分页函数会返回很多额外的数据，所以需要自定义些返回数据

<!--more-->

- 封装方法

```php
use Illuminate\Contracts\Pagination\Paginator;
function page_number(Paginator $paginator)
    {
        return [
            'total' => $paginator->total(),//总条数
            'page_size' => $paginator->perPage(),//每页的数据条数
            'current_page' => $paginator->currentPage(),//当前页页码
            'last_page' => $paginator->lastPage(),//最后一页的页码
            'items'=>$paginator->items()//分页后的数据
        ];
    }
```

- 调用

```php
$data=DB:table("xxx")->where($where)->select($columns)->paginate();
return page_number($data);
```



