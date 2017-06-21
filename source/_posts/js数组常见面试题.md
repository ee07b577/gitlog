---
title: js数组常见面试题
date: 2017-06-22 18:20:38
description: 本博客汇集了几个javascript数组的常见面试题，很多都是数组的自带函数，在数据处理中有很多使用场景，因此还需要熟练掌握。当然，考察最多的还是数组的排序和查找，本博客暂时未做收录。
tags:
- javascript
- Array
- 面试题
---

### Question 1. 把有序数组变成无序数组的函数 ###

```javascript
var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
function resort(arr) {
    return arr.sort(function(a, b) {
        var rand = Math.random()
        console.log(rand);
        return rand < 0.5;
    });
}
resort(arr);
console.log(arr);
```

### Question 2. 遍历数组的方式有哪些 ###

最传统方法：for( ; ; ){} // 代码略

forEach 方法： Array.forEach(callback)
缺点：不能break

```javascript
var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
arr.forEach(function(value, key){
	console.log(key + ': ' + value);
});
```

for-of 循环： for(var value of arr) // 注意这里迭代参数是value不是index哦

```javascript
var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
for(var value of arr){
	console.log(value);
}
```

for-in 循环：特别注意，这个是给对象用的。而且迭代参数是Key而不是value.
如果数组使用这种循环遍历，结果会是怎样的呢？执行以下代码试一下吧！

```javascript
var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
for(var key in arr){
	console.log(key + ' ' + arr[key]); // 不会把 length 函数打印出来，因为length方法在Array中是不可枚举的属性。 
}
arr.propertyIsEnumerable('length') // 打印false
```

join map reduce filter some all 方法

具体用法查看官网即可。以下写出几个示例代码，小伙伴们自己运行一下。