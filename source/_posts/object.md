title: "什么是面向对象"
date: 2015-05-27 14:01:14
tags:
- javacript
categories:
- javacript
- 面向对象
---


面试的时候还是经常会遇到的一个问题，在逛论坛的时候看到一个挺不错的回答的，所以分享下...
**首先，它是解决的一种处理方式。将问题发出方和接收方的类型高度抽象成一个个的整体，
各个整体之间产生的关系后，将会产生某些问题，对这些关系问题的处理，在于各个整体之间的方法实现（怎么突然发现这么拗口呀）
这种处理方法：整体意为对象，方法也叫函数。整个的程序设计叫做面向对象程序设计...**

传统面向对象....

```javascript
var Anim = function(){...};
Anim.prototype = {
    start:function() {
        ...
    },
    stop:function() {
        ...
    }
};

```

另一种尝试，类面向对象的编程风格

```javascript
Function.prototype.method = function(name,fn) {
    this.prototype[name] = fn;
    return this;
};//用于链式调用
var Anim = function(){};
Anim.method('start',function() {});
Anim.method('stop',function() {});

```