---
categories: 
- 编程开发
tags:
- 前端

---

#### 自定义模板

```js
cols: [
                    [{
                        field: 'id',
                        title: '编号'
                    }, {
                        field: 'title',
                        title: '姓名'
                    }, {
                        field: 'column',
                        title: '栏目',
                        templet:"#temp"
                    },
                    {
                        field: 'sort',
                        title: '排序'
                    },{
                        templet: '#opera',
                        title: '操作'
                    }]
                ]
```

上面的代码是一段渲染表头的代码！

在栏目那一列 自定义了一个temp的模板

```javascript
<script id="temp">
    {{# if (d.column=== 0) { }}
    专家
    {{# } else { }}
    人才
    {{# } }}
</script>
```

具体模板引擎语法可以点击下面的连接

https://www.layui.com/doc/modules/laytpl.html