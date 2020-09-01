---
categories: 
- 编程开发
tags:
- 前端开发 
---
```javascript
$("body").bind("keydown",function(event){
if(event.keyCode == 116) {
event.preventDefault();//阻止默认刷新
$("#main_frame").attr("src",window.frames["main_frame"].src);
}
```

<!--more-->

```javascript
$("body").bind("keydown",function(event){
if(event.keyCode == 116) {
event.preventDefault();//阻止默认刷新
$("#main_frame").attr("src",window.frames["main_frame"].src);
}
```

重点就是这个`event.preventDefault();//阻止默认刷新`

其他你可以随意操作了