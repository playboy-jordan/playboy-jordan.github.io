---
layout: post
title:  springboot中外部配置文件和加载顺序
category: springboot
excerpt: "本文主要介绍springboot中外部配置文件的加载顺序"
---
下面我们先看下如何在内部配置文件中配置项目的路劲 

```
server.servlet.context-path=/boot

```

![](https://img-blog.csdnimg.cn/20200310233406294.png)

![](https://img-blog.csdnimg.cn/20200310233452890.png)

如果我想要配置调用外部的配置文件，该怎么调用呢？ 下图是我们在e盘下面配置的一个配置文件 

![](https://img-blog.csdnimg.cn/20200310234008158.png)

我们可以通过在项目Run configuration ,argumenets:中的使用 –spring.config.location=E:/application.properties来调用这个配置文件 

![](https://img-blog.csdnimg.cn/20200310234902706.png)

![](https://img-blog.csdnimg.cn/20200310234941413.png)

我们从上面的例子中也可出如果一个配置同时存在于内部配置文件和外部配置中的时候，外部配置文件会覆盖内部配置文件。 外部配置文件其实就是对内部配置文件的一种补充，比如我们的项目已经打包了，这时候如果想要改变配置文件中某一项配置，我们就可以启用外部配置文件，这个样就很简单。如果不这样处理的话，可能我们还需要把原来的项目打包然后更改，然后再打包。 我们还可以直接通过命令来调用外部配置文件，比如下面的例子 首先通过mvn clean package -DskipTests=true 来打包， 

![](https://img-blog.csdnimg.cn/20200311001811174.png)

上面介绍的两种调用外部配置文件的方法，如果需要改变的参数比较多，我们则用上面的方法来调用配置文件，但是如果我们只想要改变某一个或者几个配置的的话，可以直接用命令来该，就不用应用外部配置文件了 

![](https://img-blog.csdnimg.cn/20200311002332694.png)

![](https://img-blog.csdnimg.cn/20200311002351319.png)

当然，这种只改变某一个参数的方法， 我们也可以在sts中通过 在项目Run configuration ,argumenets:中使用 –server.port=8883来改变 

![](https://img-blog.csdnimg.cn/20200311003056214.png)

![](https://img-blog.csdnimg.cn/20200311003208921.png)

下图是官网给出的顺序, 地址为: [spring官网配置文件顺序](https://docs.spring.io/spring-boot/docs/2.1.13.RELEASE/reference/html/boot-features-external-config.html) 

