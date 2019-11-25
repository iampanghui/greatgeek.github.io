---
layout:     post
title:	让Google 能检索到github.io 上的内容
subtitle:   
date:       2019-11-25
author: 	庞晖
header-img: img/post-bg-ios9-web.jpg
catalog: 	 true
tags: 	博客技艺
---

### 如何使Google 能检索到github.io 博客上的内容

正常搭建在Github Pages 上的博客是不会被Google 纳入检索的,毕竟它不会去检索一个 Github 仓库. 而我们的博客需要被检索才能让有需要的人看到.

使用 [Google search console](https://search.google.com/search-console/about) 可以使你的内容编入 Google 索引中,还有一系列其他的功能可以帮助你管理你的网站.

Google search console 有多种验证方式.
1. 下载它提供的一个关于验证的html 的文件,并上传你的网站的根目录下;
2. 在网站首页(即 index.html) 的head 块中添加 meta 验证信息;

### Google search console 非常易于使用
它会指导你完成整个过程的验证,并提供多种验证方式,所以操作起来非常简单.