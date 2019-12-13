---
layout:     post
title:	What is remount in Linux
subtitle:   
date:       2019-12-13
author: 	庞晖
header-img: img/post-bg-ios9-web.jpg
catalog: 	 true
tags: 	Linux
---

### What is remount in Linux

#### from book: Unix and Linux system administration handbook
In many single-user environments, the filesystem root directory starts off being mounted read-only. If **/etc** is part of the root filesystem(the usual case), it will be impossible to edit many important configuration files. To fix this problem, you'll have to begin your single-user session by remounting **/** in read/write mode. Under Linux, the command

``` # mount -o rw,remount / ```

usually does the trick.

#### from book: Linux Command Line and Shell Scripting BIBLE
**Tip:**
You can run the ```fsck``` command on unmounted filesystems only. For most filesystems, you can just unmount the filesystem to check it and then remount it when you're finished. However, because the root filesystem contains all the core Linux commands and log files, you can't unmount it on a running system.