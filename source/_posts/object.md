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

### 语义化标签
#### 标签语义化的好处
* 去掉样式或者样式丢失时页面结构依然清晰分明
* 搜索引擎会根据标签的语义确定上下文和权重问题
* 便于后期的开发以及维护，团队合作效率提高

### 用过哪些html5特性
* localstorage的使用，canvas的使用，doctype只需要简单定义，设置charset=uft-8

### ajax和跨域
* 创建一个ajax的过程：
** 创建引擎（xmlHttpRequest对象）new XMLHttpRequest or new AcitveXObject
** 事件处理函数，处理服务器的响应结果 onreadystatechange 
readyState == 4 or status == 200
responseText包含了从服务器发送的数据
每次 readyState 值的改变，都会触发 readystatechange 事件 
** 打开一个连接open(method, url, asynch)
** 发送数据send(data)
* 跨域
** 动态创建js，如jsonp的实现
** document.domain+iframe的设置
** flash的实现


* 事件代理

通过它你可以把事件处理器添加到一个父级元素上，这样就避免了把事件处理器添加到多个子级元素上。事件冒泡以及目标元素。
使用事件代理，我们可以把事件处理器添加到一个元素上，等待一个事件从它的子级元素里冒泡上来，并且可以得知这个事件是从哪个元素开始的。
** 性能要好
** 针对新创建的元素，直接可以拥有事件

* 盒模型d
有两种， IE 盒子模型、标准 W3C 盒子模型；IE的content部分包含了 border 和 padding;
盒模型： 内容(content)、填充(padding)、边界(margin)、 边框(border).

* css的position
** absolute 
        生成绝对定位的元素，相对于 static 定位以外的第一个祖先元素进行定位。 

** fixed （老IE不支持）
    生成绝对定位的元素，相对于浏览器窗口进行定位。 

** relative 
    生成相对定位的元素，相对于其在普通流中的位置进行定位。 

** static  默认值。没有定位，元素出现在正常的流中
    （忽略 top, bottom, left, right z-index 声明）。
** inherit 规定从父元素继承 position 属性的值。

* css的flex

```css

  /*flex布局（作用于容器）*/
	display: flex;

	/*水平居中（作用于容器）*/
	justify-content: center;

	/*垂直居中（作用于容器）*/
	align-items: center;
```

* 闭包
一个函数能够访问到另一个函数内的变量！
`函数作为返回值，函数作为参数传递。`

* this 
在函数中this到底取何值，是在函数真正被调用执行的时候确定的，函数定义的时候确定不了
因为this的取值是执行上下文环境的一部分，每次调用函数，都会产生一个新的执行上下文环境。

