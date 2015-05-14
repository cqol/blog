title: "学习笔记-设计模式之创建者模式"
date: 2015-05-14 19:44:10
tags:
- javacript
categories:
- javacript
- 设计模式
---

创建者模式可以将一个复杂对象的构建与其表现形式相分离，使得同样的构建过程可以创建不同的表现形式。
也就是说如果我们用了创建者模式，那么用户只需制定需要建造的类型就可以得到，而具体建造的过程和细节无需了解。上个简单例子....


```javascript
function getBeerById(id, callback) {
    //使用Id来请求数据，返回数据。
    getRequest('get', 'beer.url ? id =' + id, function(resp) {
        //callback调用responseTest
        callback(resp.responseTest)
    });
}
var elm = document.getElementById('test');
elm.addEventListener('click', getBeerByIdBridge, false);
function getBeerByIdBridge(e) {
    getBeerById(this.id, function(beer) {
        console.log('Requested beer:' + beer);
    });
}
```


根据建造者的定义，表相即是回调，也就是说区数据后如何显示和处理取决于回调函数（callback）
相应的回调函数在处理数据的时候不需要关注是如何获取数据的。
我们在jquery的ajax方法里可以看到很多的回调函数，比如`success`，`error`登回调函数，这些都是创建者模式的经典例子
说白了：创建者模式就是-获取数据与处理数据是分离的！

