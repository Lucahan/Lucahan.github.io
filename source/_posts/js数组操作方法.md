---
title: js数组操作方法
date: 2019-06-25 21:18:17
tags: 
  - js
  - 数组
categories: js
---

参考文章：<https://segmentfault.com/a/1190000019522061>

##### 1.toString

将数组转换为以逗号分隔的字符串

```js
let a = ['a','b','c'];
console.log(a.toString());//a,b,c
```

##### 2.join

与toString方法相似，不同的是，这里可以指定符号，而不是默认的逗号

```js
let a = ['a','b','c'];
console.log(a.join('*'));//a*b*c
```

##### 3.concat

将两个数组相连接，返回一个新的数组

```js
let a = [1,2,3];
let b = [4,5,6];
console.log(a.concat(b))//[1,2,3,4,5,6]
```

##### 4.push 

向数组尾部追加元素，并且修改原始数组

##### 5.pop

删除数组的最后一项并且返回

##### 6.shift

删除数组的第一项并且返回

##### 7.unshift

向数组头部追加并且修改原来的数组

##### 8.splice

此方法是通过添加，删除和插入来修改原始数组

```js
array.splice(index,[,deleteCount,ele1,...,eleN])
//index 删除数组的起点
//deleteCount 删除元素的个数
//ele1,...,eleN 要添加的元素
```

例一：两个参数

> ```js
> let colors = ['green', 'yellow', 'blue', 'purple'];
> colors.splice(0, 3);
> console.log(colors); // ["purple"]
> // deletes ["green", "yellow", "blue"]
> ```

例二：一个参数

如果只有index一个参数，那么会默认删除index后的所有参数

例三：所有参数

从索引开始，删除对应元素数，并且追加元素

```js
let schedule = ['I', 'have', 'a', 'meeting', 'tommorrow'];
// removes 4 first elements and replace them with another
schedule.splice(0, 1, 'we', 'are', 'going', 'to', 'swim');
console.log(schedule); 
//["we", "are", "going", "to", "swim", "have", "a", "meeting", "tommorrow"]
```

##### 9.slice

与splice相似，但是slice会复制数组的指定部分并且返回，而不会改变原来的数组

array.slice(start,end)

```js
let numbers = [1, 2, 3, 4]
numbers.slice(0, 3)
// returns [1, 2, 3]
console.log(numbers) //返回原始数组
```

##### 10.split

把字符串分隔成子串并且作为数组进行返回

```js
var  k = 'a,b,c,d';
k.split(',')
//["a", "b", "c", "d"]
```

##### 11.indexOf

在数组中查找项目，并且返回索引，否则返回-1

##### 12.lastIndexOf

在数组中反向查找项目，并且返回索引，否则返回-1

##### 13.filter

如果数组符合某个条件，那么会创建一个新的数组

```js
var c = [1,2,3,4,5,6,7,8]
var d = c.filter(code => code > 4)
console.log(d) //[5, 6, 7, 8]
```

##### 14.map

此方法可以通过操作数组中的值来创建新的数组

```js
// 将美元符号添加到数字前面
const numbers = [10, 3, 4, 6];
const dollars = numbers.map( number => '$' + number);
console.log(dollars);
// ['$10', '$3', '$4', '$6'];
```

##### 15.reduce

常用的使用方法是用来求数组和，数组乘积；

较为高级的用法参见下文：https://www.jianshu.com/p/e375ba1cfc47

> > > > > ```js
> > > > > var arr = [1, 2, 3, 4];
> > > > > var sum = arr.reduce(function(prev, cur, index, arr) {
> > > > >     console.log(prev, cur, index);
> > > > >     return prev + cur;
> > > > > })
> > > > > console.log(arr, sum);
> > > > > /**
> > > > > *打印结果
> > > > > 1 2 1
> > > > > 3 3 2
> > > > > 6 4 3
> > > > > [1, 2, 3, 4] 10
> > > > > */
> > > > > ```
> > > > >
> > > > > ##### 16.forEach
> > > > >
> > > > > 不用多说了，遍历数组

##### 17.every

检查数组中是否所有的项都符合指定条件，符合返回true，不符合返回false

```js
var num = [1,2,3,4,5,6,7,8];
var res = num.every(item => item > 5);
console.log(res);//false
```

##### 18.some

检查数组中只要有一项符合指定条件，则返回true，不符合返回false

```js
var num = [1,2,3,4,5,6,7,8];
var res = num.some(item => item > 5);
console.log(res);//true
```

19.includes

与some方法相似，检查数组中是否包含特定项

```js
let users = ['paddy', 'zaddy', 'faddy', 'baddy'];
users.includes('baddy'); // returns true
```



##### 总结

- **toString()** - 将数组转换为以逗号分隔的字符串。
- **join()** - 将所有数组元素组合成一个字符串。
- **concat** - 将两个数组组合在一起，或者将更多项添加到数组中，然后返回一个新数组。
- **push()** - 将项目添加到数组的末尾，**改变**原始数组。
- **pop()** - 删除数组的最后一项并**返回**
- **shift()** - 删除数组的第一项并**返回**
- **unshift()** - 将一个项添加到数组的开头，**改变**原始数组。
- **splice()** - 通过添加，删除和插入元素**修改**一个数组。
- **slice()** - 复制数组的给定部分，并将复制的部分作为新数组返回。 **它不会改变原始数组。**
- **split()** - 将一个字符串分成子串并将它们作为数组返回。
- **indexOf()** - 查找数组中的项目并返回其**索引**，如果没找到则返回`-1`
- **lastIndexOf()** - 从右到左查找项目并返回找到的最后一个索引。
- **filter()** - 如果数组的项目符合某个条件，则创建一个新数组。
- **map()** - 通过操纵数组中的值来创建一个新数组。
- **reduce()** - 根据数组中的单个值进行计算。
- **forEach()** - 遍历数组，将函数作用于数组中的所有项
- **every()** - 检查数组中的所有项是否都符合指定的条件，如果符合则返回 `true`，否则返回 `false`。
- **some()** - 检查数组中的项（一个或多个）是否符合指定的条件，如果符合则返回 true，否则返回 false。
- **includes()** - 检查数组是否包含某个项目。

附：

MDN参考文档：https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array