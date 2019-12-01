---
layout:     post
title:	Linux下使用configure/make/make install安装软件提示文件缺失错误
subtitle:   
date:       2019-11-29
author: 	庞晖
header-img: img/post-bg-ios9-web.jpg
catalog: 	 true
tags: 	Linux
---

### configure 命令执行过程中提示文件缺失
```
openssl/ssl.h: No such file or directory
```
Unix 文件I/O系统并不区别文件与目录.

产生此类错误,常常是由于运行环境中缺失相关的库文件导致的. 上述错误就是由于libssl-dev 库的缺失导致的.
这里发生的问题需要用到一些关于```链接```的知识.

### 链接

共享库(shared library)是一个目标模块,在运行时,可以加载到任意的存储器地址,并和一个在存储器中的程序链接起来.这个过程称为动态链接(dynamic linking),是由一个叫做动态链接器(dynamic linker)的程序来执行的.

共享库也称为共享目标(shared object), 在Unix系统中通常用```.so```后缀来表示. windows 下称为DLL(动态链接库).

安装的目标软件中引用了共享库时, 而运行环境却缺失这个库时,就会提示文件缺失.


### 参考来源
1. 深入理解计算机系统