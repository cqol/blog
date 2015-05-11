title: "notes"
date: 2015-05-08 14:27:21
tags:
- javacript
categories:
- javacript
- 学习笔记
---

### 各种`apply`的妙用

合并数组
```javascript
var a=[1,2,3], b=[4,5,6]
Array.prototype.push.apply(a, b);
//a = [1,2,3,4,5,6];
```
数组对象转数组
```javascript
var arr = Array.prototype.slice.call(arguments);
```

用0补全位数
```javascript
//TODO: 有问题！
function preFixInt(num, length) {
  return (num / Math.pow(10,length)).toFixed(length).substr(2);
}
```

将一个数组插入另一个数组的指定位置
```javascript
var a=[1,2,3,7,8,9], b=[4,5,6], insertIndex=3;
a.splice.apply(a, Array.prototype.concat(insertIndex, 0, b));
//a = [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

快速取数组最大和最小值
```javascript
Math.max.apply(Math, [1,2,3]); //3
Math.min.apply(Math, [1,2,3]); //1
```

### 有意思的技巧

反转字符串
```javascript
var str = "aaaaabbbccccbddddd";
console.log(str.split("").reverse().join(""));
```
数组去重
```javascript
funciton unq(a) {
  var b = [], c = {}, i;
  for (i in a) {
    c[a[i]] || (b.push(a[i])), c[a[i]] = true;
  }
  return b;
}

Array.prototype.unq = function () {
  var tempArr = [];
  var tempObj = {};
  for (var i=0; i<this.length; i++) {
    if (!(this[i] in tempObj) || !(this[i] === tempObj[this[i]])) {
      tempArr.push(this[i]);
      tempObj[this[i]] = this[i];
    }
    
  }
  return tempArr;
}
```

生成随机数
```javascript
function randomFrom(low, up) {
  var choices = up - low + 1;
  return Math.floor(Math.random()*choices + low);
}
```