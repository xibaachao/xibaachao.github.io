---
categories: 
- 编程开发
tags:
- 前端开发
---
#### 图片
![](/images/2020/4.gif)

#### 前端代码
```html
<div class="layui-fluid">
    <div class="layui-card">
        <div class="layui-form layui-card-header layuiadmin-card-header-auto">
            <div class="layui-form-item" lay-filter="search_from">
                <div class="layui-inline">
                    <label class="layui-form-label">关键字</label>
                    <div class="layui-input-inline">
                        <input type="text" name="key" placeholder="请输入" autocomplete="off" class="layui-input">
                    </div>
                </div>
                <div class="layui-inline">
                    <button class="layui-btn layuiadmin-btn-list" lay-submit lay-filter="search">
                        <i class="layui-icon layui-icon-search layuiadmin-button-btn"></i>
                    </button>
                </div>
            </div>
        </div>
        <div class="layui-card-body">
            <div style="padding-bottom: 10px;">
                <button class="layui-btn layuiadmin-btn-list" data-type="batchdel" id="refresh">刷新</button>
                <button class="layui-btn layuiadmin-btn-list" data-type="add" id="add">添加</button>
            </div>
            <table id="list" lay-filter="list"></table>
            <script type="text/html" id="opera">
                <a class="layui-btn layui-btn-normal layui-btn-xs" lay-event="edit"><i
                        class="layui-icon layui-icon-edit"></i>编辑</a>
                <a class="layui-btn layui-btn-danger layui-btn-xs" lay-event="del"><i
                        class="layui-icon layui-icon-delete"></i>删除</a>
            </script>
        </div>
    </div>
</div>
<script src="/layuiadmin/layui/layui.js"></script>
<script>
    layui.config({
        base: '/layuiadmin/'
    }).use(['table'], function () {
        var table = layui.table,
            form = layui.form,
            $ = layui.$;
        form.on('submit(search)', function (data) {
            table.reload("list", {
                page: {
                    curr: 0
                },
                where: data.field
            })
        });
        var renderTable = function () {
            table.render({
                elem: '#list',
                method: "post",
                where: {
                    "_token": "{{csrf_token()}}" //其他参数
                },
                url: '{{route("admin.admin.data")}}',
                page: true,
                response: {},
                done: function (res, curr, count) {
                },
                limit: 30,
                cols: [
                    [{
                        field: 'id',
                        title: '编号'
                    }, {
                        field: 'username',
                        title: '姓名'
                    }, {
                        templet: '#opera',
                        title: '操作'
                    }]
                ]
            });
        };
        renderTable();
        table.on('tool(list)', function (obj) {
            var data = obj.data;
            var layEvent = obj.event;
            if (layEvent === 'del') {
                //执行删除的方法
            }
            if (layEvent === "edit") {
               //执行编辑的方法
            }

        })
        $('#refresh').click(function () {
            renderTable();
        });
        $('#add').click(function () {
           //添加的方法
        });
    });
</script>

```



#### 后端数据返回格式

```json
{
	"code": 0,//必须为0
	"data": [{ 
		"id": 1,
		"username": "admin"
	}],
	"msg": "请求成功",
	"count": 1 //数据总量
}
```

