---
categories: 
- 编程开发
tags:
- CSS
---
#### 图片居中

![](/images/2020/3.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        *{margin: 0;padding: 0;}
        li{
            background-color: aqua;
            list-style: none;
            float: left;
            margin: 5px;
            width: 400px;
            height: 400px;
        }
        .img_box{
            width: 400px;
            height: 400px;
            text-align: center;
            vertical-align: middle;
            display: table-cell;
        }
        .img_box img{
            max-width: 100%;
            max-height: 100%;
        }
    </style>
</head>
<body>
    <ul>
        <li>
            <div class="img_box">
                <img src="1.jpg">
            </div>           
        </li>
        <li class="img_box">
            <div class="img_box">
                <img src="IMG_20190704_101448.jpg">
            </div>   
        </li>
        <li class="img_box">
            <div class="img_box">
                <img src="2.jpeg">
            </div>  
        </li>
    </ul>   
</body>
</html>
```

注：

```html
.img_box{
            width: 400px;
            height: 400px;
            text-align: center;
            vertical-align: middle;
            display: table-cell;
        }
        .img_box img{
            max-width: 100%;
            max-height: 100%;
        }
```

.img_box ：表示图片的父级元素 需要设置父级元素的高、宽、居中对齐、垂直对齐、并将元素设置成表格单元格的模式。

.img_box img：图片则将最大宽高度设置成100%就可以了。





