---
layout:     post
title:	windows平台中上传文件来linux服务器/下载文件到本地
subtitle:   
date:       2019-12-2
author: 	庞晖
header-img: img/post-bg-ios9-web.jpg
catalog: 	 true
tags: 	Linux
---

### 使用Linux中的 rz,sz命令

想要在**windows**平台下与**linux**服务器交互,可以使用``` lrzsz```工具.

```lrzsz``` 该工具的是以**linux**服务器作为第一人称的, ```rz```表示我想要接收一个文件; ```sz```表示我想要发送一个文件.

```rz```:运行该命令会弹出一个文件选择窗口,从本地选择文件上传到服务器(receive),即**windows**上传文件到**linux**服务器.

```sz```:将选定的文件发送(send)到本地机器,即从**linux**服务器下载到**windows**.
