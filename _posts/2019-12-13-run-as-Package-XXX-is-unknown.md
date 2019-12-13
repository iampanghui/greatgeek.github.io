---
layout:     post
title:	run-as: Package 'XXX' is unknown
subtitle:   
date:       2019-12-13
author: 	庞晖
header-img: img/post-bg-ios9-web.jpg
catalog: 	 true
tags: 	Android
---

### NDK debugging does not start: "package is unknown"
This is a known bug of the Android platform. When you try to debug your NDK-based app, gdbserver fails to start and a message like below is shown:

```
run-as: Package 'XXX' is unknown
```

### Works for Nexus s
#### Add the set-uid bit to the run-as binary:
```bash
su
```
```bash
mount -o remount,rw /system
```
```bash
chmod 4750 /system/bin/run-as
```
###参考来源
[NDK debugging does not start: "package is unknown"](http://visualgdb.com/KB/?ProblemID=nopkg)