---
categories: 
- 编程开发
tags:
- 前端开发
---
ueditor 由于z-index设置过高的问题，时常会挡住其他的表单元素

<!--more-->

### 临时修改

```javascript

<div class="layui-form-item" style="position: relative;z-index: 10000;">
     <select name="cid" lay-verify="cid" required id="L_cid">
          <option value="" >请选择</option>
     </select>
</div>
//
style="position: relative;z-index: 10000;"
```

### 修改全局

在`config.js`文件里搜索`zIndex`

在这里就可以修改它的层数

改为0就可以了