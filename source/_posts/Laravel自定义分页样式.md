---
categories: 
- 编程开发
tags:
- PHP

---

`Laravel` 的分页组件默认为 `Bootstrap` 的分页样式，但如果我们用的并不是 `Bootstrap` 或者说分页的 `HTML`结构不一样，这时我们需要自定义分页。其实 `Laravel` 的分页组件是非常的灵活，可以通过几种方法去实现我们的需求。

<!--more-->

### 创建分页视图

在 `resources/views` 目录下创建 `pagination` 目录，并创建一个视图`default.blade.php` 。添加一下代码：

```php
<div class="pagination">
    <ul>
        <li class="previous {{ ($paginator->currentPage() == 1) ? ' disabled' : '' }}">
            <a href="{{ $paginator->url(1) }}">第一页</a>
        </li>
        <li class="">
            <a href="{{ $paginator->previousPageUrl() }}">上一页</a>
        </li>
        @for ($i = 1; $i <= $paginator->lastPage(); $i++)
            <li class="{{ ($paginator->currentPage() == $i) ? ' active' : '' }}">
                <a href="{{ $paginator->url($i) }}">{{ $i }}</a>
            </li>
            @endfor
            <li>
                •••
            </li>
            <li class="next">
                <a href="{{ $paginator->nextPageUrl()}}">
                    下一页
                </a>
            </li>

            <li>
                跳转&nbsp;<input type="text" id="page" style="text-align: center;">&nbsp;页
            </li>
            <li class="active">
                <a href="javascript:go();">GO</a>
            </li>
    </ul>
</div>
<script>
    function go(id){
        var page = document.getElementById("page").value;
        var url = window.location.href+"?&page="+page;
        window.location.href=url;
    }
</script>
```

### 其他常用常用函数说明

`$paginator->currentPage()`：获取当前页

`$paginator->lastPage()`：获取尾页

`$paginator->url($page)`：获取页码的URL

具体参数参考：https://learnku.com/docs/laravel/7.x/pagination/7495#paginator-instance-methods