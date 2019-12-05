---
layout:     post
title:	Spring的DTD验证与Schema验证
subtitle:   
date:       2019-12-4
author: 	庞晖
header-img: img/post-bg-ios9-web.jpg
catalog: 	 true
tags: 	Spring
---

### Spring 的DTD验证与Schema验证

#### DTD验证
在Spring 1.x 版本中,使用DTD来验证XML配置文件,一个典型的XML文件如下:
```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE beans PUBLIC "-//SPRING//DTD BEAN 2.0//EN"
        "http://www.springframework.org/dtd/spring-beans-2.0.dtd">

<beans>

<!-- bean definitions here -->

</beans>
```
Spring2.0 版本仍然可以继续使用上面的DTD验证,不过,某些新的特性(如 scope属性) 将无法通过DTD验证,从而导致Spring容器启动失败.对于 Spring2.0 版本,强烈推荐使用 Schema 验证,典型的XML文件如下.

```
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="
        http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <!-- bean definitions here -->

</beans>
```

### 参考来源

[40. XML Schema-based configuration](https://docs.spring.io/spring/docs/4.2.x/spring-framework-reference/html/xsd-configuration.html)

