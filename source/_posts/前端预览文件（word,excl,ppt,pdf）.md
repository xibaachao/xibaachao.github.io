---
categories: 
- 编程开发
tags:
- 前端开发
---

#### 1、a标签预览

```html
<a href="文件地址">点击下载</a>
```

注： 好像只能预览pdf文件，而且还要看浏览器是否兼容，是否支持预览

#### 2、js 插件

插件：[jquery.media.js](https://github.com/malsup/media/blob/master/jquery.media.js)

```html
<script type="text/javascript" src="jquery.min.js"></script>  
<script type="text/javascript" src="jquery.media.js"></script>

<body>
   <div id="preview"></div>
</body>
<script type="text/javascript">  
 $('#preview').media({
        width: '100%',
        height: '100%',	
        autoplay:true,
        src:'文件地址'
 }); 
</script>
```

#### 3、在线预览

https://view.officeapps.live.com/op/view.aspx?src=网络地址

```
<iframe src='https://view.officeapps.live.com/op/view.aspx?src=网络地址' width='100%' height='100%' frameborder='1'>
</iframe>
```

