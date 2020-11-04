---
layout: post
title:  Springboot整合外置tomcat及使用jsp开发
category: springboot
excerpt: "本文主要介绍springboot整合tomcat和jsp开发"
---
Sprngboot默认是不支持使用jsp开发的，官方都推荐使用模板引擎。如果我们要是使用jsp开发的，必须打成war包，以为springboot内置的tomcat只能执行jar包，不能执行war包，所以我们要打成war包。 我们先来建立一个springboot项目，可以参考之前的连接： [如何建立spirngboot项目](https://blog.csdn.net/weixin_44853669/article/details/104827150) 

![](https://img-blog.csdnimg.cn/20200324232712348.png)

项目建好之后，我们在pom文件中知道tomcat 

![](https://img-blog.csdnimg.cn/20200324232916226.png)

```
<scope>provided</scope>

```

这个级别是一个小细节，这个级别意味着项目打包的时候不打包这个tomcat,为啥不打包这个tomcat吗？因为这个tomcat是内置的tomcat，以前我们直接建立springbootyong 用jar包的时候，必须把这个内置的tomcat和其他jar一起打成一个大的jar，这样项目才可以执行。但是现在我们是war包，用的是外置的tomcat,所以不用打包这个内置的tomcat了。 接下来，我们就要建立web项目所需的目录结构 webapps/WEB-INF(需要) webapps/WEB-INF/web.xml (不需要) webapps/index.jsp 

![](https://img-blog.csdnimg.cn/20200324234311868.png)

部署到外置Tomcat中并且启动 

![](https://img-blog.csdnimg.cn/20200324234552556.png)

![](https://img-blog.csdnimg.cn/20200324234607335.png)

![](https://img-blog.csdnimg.cn/20200324234644527.png)

如何本地没有tomcat 的话，可以去官网下载一个，解压版和安装的都可以

未完待续!!!