---
title: js闭包问题
date: 2017-06-21 18:08:27
description: 第一题是题目原型，后面都是拓展变形。考察点可以参考本博客底部的关键词，小伙伴们自行体会~
tags:
- 闭包
- javascript
- setTimeout
- ES2015
- 面试题
---

### Question 1 ###

代码
```javascript
function foo() {
    for (var i = 0; i < 10; i++) {
        setTimeout(function() {
            console.log(i);
        }, 1000);
    }
}
foo();
```
运行结果

	1s钟后连续打印10个10

### Question 2 ###

代码
```javascript
function foo() {
    for (var i = 0; i < 10; i++) {
    	var j = i;
        setTimeout(function() {
            console.log(j);
        }, 1000);
    }
}
foo();
```
运行结果

	1s钟后连续打印10个9

### Question 3 ###

代码
```javascript
function foo() {
    for (var i = 0; i < 10; i++) {
        setTimeout(function() {
            console.log(i);
        }, 1000 * ( i + 1));
    }
}
foo();
```
运行结果

	1s钟后打印一个10，以后每隔1s钟打印一个10，共打印10个10

### Question 4 ###

代码
```javascript
function foo() {
    for (var i = 0; i < 10; i++) {
        (function(j) {
            setTimeout(function() {
                console.log(j);
            }, 1000);
        })(i)
    }
}
foo();
```
运行结果

	1s钟后连续打印0-9

### Question 5 ###

代码

```javascript
function foo() {
    for (let i = 0; i < 10; i++) {
        setTimeout(function() {
            console.log(i);
        }, 1000);
    }
}
foo();
```
运行结果

	1s钟后连续打印0-9