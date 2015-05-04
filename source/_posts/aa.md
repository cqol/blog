title: "aa"
date: 2015-05-01 01:04:36
tags:
- javacript
categories:
- javacript
- 设计模式
---

```bash
var myTest = {
　　property1:"something";
　　property2:"something else";
　　method1:function(){
　　　　console.log("Hello world!");
　　}
}
```

cqol在扩展对象，可以添加自己的私有成员和方法，使用闭包的形式在其内部封装这些变量和函数声明，只暴露你想要暴露的public成员和方法

```bash
var myTest = function() {
　　//私有变量和方法
    var pVariable = "some private";
    function showPrivate() {
        console.log(pVariable);
    }
    return {
        publicMethod: function() {
            showPrivate();
        },
        publicVar: "the public can see this"
    };
}
```
使用的时候`var test= myTest(); test.publicMethod();//输出some private`
我们也可以在使用的时候才初始化！我们可以再另外一个构造函数里来初始化这些代码。