---
title: session共享
date: 2018-11-06 14:10:38
tags: [session,redis,spring session]
categories:
 -session
---
现在的项目基本都是分布式系统，涉及到session共享，保证用户的无感知；
1. nginx + tomcat
  - nginx 配置同一用户分配到同一Tomcat上，使用Tomcat session；
2. tomcat + redis
  - Tomcat 插件配置session存入Tomcat，避免修改代码
3. request session
   - 封装request(HttpServletRequestWrapper),调用httpsession
   - 封装session(HttpSessionWrapper),实现自己的session管理
   - 自定义filter，设置如何拦截获取sessionID
   - 配置filter生效
4. shiro session(https://blog.csdn.net/qq_34021712/article/category/8000629)
  shiro不仅提供了权限管理功能，而且也提供了会话管理功能，可以自定义sessionDao来实现session共享功能。其实shiro就是对request session进行了封装实现。
  - 自定义sessionDao(AbstractSessionDAO)
  - 自定义DefaultWebSessionManager解决频繁执行doreadsession读取session属性；
  - 自定义SimpleSession解决频繁写入session；
  - 自定义缓存实现
5. spring session
  有spring session介入管理session对象
  - servler的httpsession替换为spring-session的httpsession
  - 配置spring-data-redis连接地址
  - 启用RedisHttpSessionConfiguration,默认使用cookie关联sessionID，若使用header则启用HeaderHttpSessionStrategy
