title: 学习笔记-设计模式之单例模式
date: 2015-04-29 11:19:16
tags:
- javacript
categories:
- javacript
- 设计模式
---

所谓单例模式就是在保证一个类只有一个实例，实现的方法一般是先判断实例存在否，如果存在直接返回，如果不存在就创建了再返回。
那如何创建一个单例呢？其中最简单的一个方式是使用对象字面量的方法，其字面量可以包含大量的属性与方法。


```bash
var myTest = {
　　property1:"something";
　　property2:"something else";
　　method1:function(){
　　　　console.log("Hello world!");
　　}
}
```


在扩展对象，可以添加自己的私有成员和方法，使用闭包的形式在其内部封装这些变量和函数声明，只暴露你想要暴露的public成员和方法

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

```bash
var myTest = function() {
    var instantiated;
    function init() {//这里定义单例代码
        return {
            publicMethod: function() {
                console.log("Hello World");
            },
            publicProperty: "something testPublic"
        }
    };
    return {
        getInstance: function() {
            if(!instantiated) {
                instantiated = init();
            }
            return instantiated;
        }
    };
}
```
调用的时候`var bbb = myTest1();bbb.getInstance().publicMethod();//输出Hello World`
单例模式.一般用在系统间各种模式的通信协调上。下面是一个单例模式的最佳实践

```bash
var BestTest = function() {
    //单例的一些参数集合
    function bestTest(args) {
        var args = args || {};
        this.name = "bestTest";
        this.pointX = args.pointX || 6;
        this.pointY = args.pointY || 10;
    }
    var instance //实例的容器
    var _static = {
        name: "bestTest",
        getInstance: function(args) {
            if(instance === undefined) {
                instance = new bestTest(args);
            }
            return instance;
        }
    }
    return _static;
}

var sss = BestTest().getInstance({ pointX: 77 });
console.log(sss.pointX); // 输出 77 
```
