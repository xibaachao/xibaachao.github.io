---
categories: 
- 编程开发
tags:
- 前端开发
---

sort()方法实现对象数组的排序,sort()方法会改变原数组，默认按unicode码顺序排列

<!--more-->

### 对象数组排序

```javascript
var arr = [
            { name:"小明", age:12 },
            { name:"小红", age:11 },
            { name:"小刚", age:15 },
            { name:"小华", age:13 }
        ];
        
function compare(p){ //这是比较函数
    return function(m,n){
        var a = m[p];
        var b = n[p];
        return a - b; //升序
    }
}
arr.sort(compare("age"));
console.log(arr); 
//结果如下： 
//[{name: "小红", age: 11}, 
//{name: "小明", age: 12},
//{name: "小华", age: 13}, 
//{name: "小刚", age: 15}]
```

### 数组排序

- 降序

```javascript
var arr = [2,3,13,17,4,19,1];
arr.sort(function(a,b){ // 这是比较函数
    return b - a;    // 降序
})
console.log(arr) // 结果：[19, 17, 13, 4, 3, 2, 1]
```

- 升序

```javascript
var arr = [2,3,13,17,4,19,1];
arr.sort(function(a,b){ // 这是比较函数
    return a-b;    // 降序
})
console.log(arr) // 结果：[1, 2, 3, 4, 13, 17, 19]

```

### 时间排序

```javascript
arr.sort(function(a,b){
	return Date.parse(a.createTime) - Date.parse(b.createTime);
});
```



