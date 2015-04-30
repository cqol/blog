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