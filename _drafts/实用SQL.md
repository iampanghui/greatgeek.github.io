---
layout:     post
title:	实用SQL
subtitle:   
date:       2019-11-27
author: 	庞晖
header-img: img/post-bg-ios9-web.jpg
catalog: 	 true
tags: 	SQL
---

### MySQL的服务器与客户端
实际上,安装完MySQL后,除了MySQL Server,即真正的MySQL服务器外,还附赠了一个MySQL程序. MySQL Client是一个命令行客户端, 可以通过MySQL Client登录MySQL,然后输入SQL语句并执行.

通过Shell终端, 输入命令```mysql -u root -p```, 提示输入口令,输入正确即可连上MySQL Server, 同时提示符变为 ```mysql>```:

输入 ```exit``` 断开与MySQL Server的连接并返回到命令提示符. 但此时MySQL Server 并未关闭,仍在后台运行.

### linux下开启与关闭MySQL服务的方式
**服务方式**
```bash
service mysql start/stop
```