---
layout:     post
title:	JavaScript的特点
subtitle:  
date:       2019-11-28
author: 	庞晖
header-img: img/post-bg-ios9-web.jpg
catalog: 	 true
tags: 	JavaScript
---

### 多行字符串
由于多行字符串用```\n```写起来比较费事,所以最新的ES6标准新增了一种多行字符串的表示方法, 用反引号``` ` ```表示:

```
`这是一个
多行
字符串`;
```

### 模板字符串
这种模板字符串有些类似```bash```里用$符引用变量的方式:
```
var name = '小明';
var age = 20;
var message = `你好, ${name}, 你今年${age}岁了!`;
```
而```bash```中的花括号```{}```, 可用作文件名扩展, 例如将 t.txt 备份到 t.bak中:
```bash
cp t.{txt,bak}
```
上述命令与``` cp t.txt t.bak ``` 等价.

### 数组
JavaScript的```Array```可以包含任意数据类型,并通过索引来访问每个元素.要取得```Array```的长度,直接访问```length```属性.
```
var arr = [1, 2, 3.14, 'Hello', null, true];
arr.length; // 6
```
**请注意**, 直接给```Array```的```length```赋一个新的值会导致```Array```大小的变化:
```
var arr = [1, 2, 3];
arr.length; // 3
arr.length = 6;
arr; // arr变为[1, 2, 3, undefined, undefined, undefined]
arr.length = 2;
arr; // arr变为[1, 2]
```
**请注意**,如果通过索引赋值时,索引超过了范围,同样会引起```Array```大小的变化:
```
var arr = [1, 2, 3];
arr[5] = 'x';
arr; // arr变为[1, 2, 3, undefined, undefined, 'x']
```

大多数其他编程语言不允许直接改变数组的大小,越界访问索引会报错.然而,JavaScript的```Array```却不会有任何错误. 在编写代码时,不建议直接修改```Array```的大小,访问索引时要确保索引不会越界.

### 数组集成了字符串,栈,队列的功能
#### slice
```slice()```就是对应String的```substring()```版本,它截取```Array```的部分元素, 然后返回一个新的```Array```:
```
var arr = ['A', 'B', 'C', 'D', 'E', 'F', 'G'];
arr.slice(0, 3); // 从索引0开始，到索引3结束，但不包括索引3: ['A', 'B', 'C']
arr.slice(3); // 从索引3开始到结束: ['D', 'E', 'F', 'G']
```
注意到```slice()```的起止参数包括开始索引，不包括结束索引(**是一个前闭后开区间**)。

如果不给```slice()```传递任何参数，它就会从头到尾截取所有元素。利用这一点，我们可以很容易地复制一个```Array```：

```
var arr = ['A', 'B', 'C', 'D', 'E', 'F', 'G'];
var aCopy = arr.slice();
aCopy; // ['A', 'B', 'C', 'D', 'E', 'F', 'G']
aCopy === arr; // false
```
#### push和pop
```push()```向```Array```的末尾添加若干元素,```pop()```则把```Array```的最后一个元素删除掉.

#### unshift和shift
```unshift()```向```Array```的头部添加若干元素,使用```unshift()```方法, ```shift()```方法则把```Array```的第一个元素删掉.

### JavaScript的对象
JavaScript的对象是一种无序的集合数据类型, 它由若干的键值对组成.

```
var xiaoming = {
    name: '小明',
    birth: 1990,
    school: 'No.1 Middle School',
    height: 1.70,
    weight: 65,
    score: null
};
```

如果属性名包含特殊字符,就必须用``` ' ' ```括起来:

```
var xiaohong = {
    name: '小红',
    'middle-school': 'No.1 Middle School'
};
```
访问属性是通过 ``` .```操作符完成的, 但访问带特殊字符的属性名需要用```['xxx']```来访问.
```
xiaohong['middle-school']; // 'No.1 Middle School'
xiaohong['name']; // '小红'
xiaohong.name; // '小红'
```

实际上JavaScript对象的所有属性都是字符串,不过属性对就的值可以是任意数据类型. 为了解决属性必须是字符串而不能是其他数据类型, 引入了```Map```类型.

**注意:** JavaScript规定,访问不存在的属性不报错,而是返回```undefined```.

### iterable
遍历```Array```可以采用下标循环,遍历```Map```和```Set```就无法使用下标.为了统一集合类型, ES6标准引入了新的```iterable```类型, ```Array```, ```Map```和```Set```都属于```iterable```类型.

**问:** ```for...of```循环和```for...in```循环有何区别?

```for...in```循环由于历史遗留问题,它遍历的实际上是对象的属性名称. 一个```Array```数组实际上也是一个对象,它的每个元素的索引被视为一个属性.

具有```iterable```类型的集合可以通过新的```for...of```循环来遍历.

## 函数


### 参考来源:
[字符串](https://www.liaoxuefeng.com/wiki/1022910821149312/1023020952022784)
