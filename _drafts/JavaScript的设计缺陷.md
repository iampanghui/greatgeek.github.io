---
layout:     post
title:	JavaScript的设计缺陷
subtitle:   
date:       2019-11-27
author: 	庞晖
header-img: img/post-bg-ios9-web.jpg
catalog: 	 true
tags: 	JavaScript
---

### 相等运算符
第一种是```==``` 比较, 它会自动转换数据类型再比较,很多时候,会得到非常诡异的结果;

第二种是```===```比较,它不会自动转换数据类型,如果数据类型不一致,返回 ```false```,如果一致,再比较;

### null与undefined
JavaScript的设计者希望用```null```表示一个空的值,而```undefined```表示值未定义. 事实证明, 这并没有什么用, 区分两者的意义不大. 大多数情况下,我们都应该用```null```. ```undefined```仅仅在判断函数参数是否传递的情况下有用.

### strict 模式
JavaScript在设计之初,为了方便初学者学习,并不强制要求用```var```申明变量.这个设计错误带来了严重的后果:如果一个变量没有通过```var```申明就被使用,那么该变量就自动被申明为全局变量:

```JavaScript
i = 10; // i现在是全局变量
```

在同一个页面的不同JavaScript文件中,如果都不用```var```申明,恰好都使用了变量 ```i```,将造成变量```i```互相影响,产生难以调试的错误结果.

使用```var```申明的变量则不是全局变量,它的范围被限制在该变量被申明的函数体内,同名变量在不同的函数体内互不冲突.

为了修补JavaScript这一严重的设计缺陷,ECMA 在后续规范中推出了strict模式, 在strict模式下运行的 JavaScript代码,强制通过```var```申明变量,未使用```var```申明变量就使用的,将导致运行错误.

启用strict模式的方法是在JavaScript代码的第一行写上:

```JavaScript
'use strict';
```

这是一个字符串,不支持strict模式的浏览器会把它当作一个字符串语句来执行,支持strict模式的浏览器将开启strict模式运行JavaScript.

### 数组越界访问索引不会报错
大多数其他编程语言不允许直接改变数组的大小，越界访问索引会报错。然而，JavaScript的Array却不会有任何错误。在编写代码时，不建议直接修改Array的大小，访问索引时要确保索引不会越界。

### 访问对象不存在的属性不会报错
JavaScript规定,访问不存在的属性不报错,而是返回```undefined```.

### JavaScript对象的键必须是字符串
JavaScript的默认对象表示方式```{}```可以视为其他语言中的```Map```或```Dictionary```的数据结构, 即一组键值对. 一个问题是JavaScript 的对象的键必须是字符串, 但实际上Number或者其他数据类型作为键也是非常合理的.

为了解决这个问题, 最新的ES6规范引入了新的数据类型```Map```

