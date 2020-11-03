---
layout: post
title:  Springboot基础之Springboot日志处理
category: springboot
excerpt: "本文主要介绍springboot中日志的处理"
---
springboot默认的日志框架是slf4j和logback，而且是帮我们配置好的，我只需要直接使用就可以了。

![](https://img-blog.csdnimg.cn/20200311225359527.png)

从上图中，我们可以看到我们一共写了5行日志，但是只打印了三行，说明默认的只打印info级别以上的日志。 日志级别： TRACE< DEBUG< INFO<WARN< ERROR< FATAL<OFF 那我们可以更改打印级别吗？当然可以，方法如下： 

![](https://img-blog.csdnimg.cn/20200311230311493.png)

![](https://img-blog.csdnimg.cn/20200311230358947.png)

配置文件中的公式是:logging.level.主配置类所在包=级别 我们还可以通过配置来吧日志输出到文件中， 

```
logging.file=springboot.log

```

当时这种方法是使用的相对路径，最后文件是存放在项目的根目录中 

![](https://img-blog.csdnimg.cn/20200311231401758.png)

![](https://img-blog.csdnimg.cn/20200311231422211.png)

上面的通过相对路径放到项目的根目录，我们也可以通过绝对路径方法其他地方，比如： 

```
logging.file=D:/springboot.log

```

![](https://img-blog.csdnimg.cn/2020031123211845.png)

![](https://img-blog.csdnimg.cn/20200311232135448.png)

那我们可以将日志方放到某一个地方的某一个文件夹 中吗？看下面的例子： 

![](https://img-blog.csdnimg.cn/20200311232701631.png)

![](https://img-blog.csdnimg.cn/20200311232717186.png)

答案是明显可以的，而且默认的文件名字是spring.log，还有如果没有创建文件夹的话，会自动创建文件夹。 如果我们想要设置日志的格式，该怎么设置呢？ 在控制台中使用: 

```
logging.pattern.console=%d{yyyy-MM-dd} [%thread] %-5level %logger{50} - %msg%n

```

解释如下：
%d:日期时间
%thread：线程名
%-5level： 显示日志级别,-5表示从左显示5个字符宽度
%logger{50} :设置日志长度 ，例如o.s.w.s.m.m.a.
%msg：日志消息
%n ：回车

在文件中使用:

```
logging.pattern.file=%d{yyyy-MM-dd} ** [%thread] ** %-5level ** %logger{50}** %msg%n

```

解释跟上面差不多。 

![](https://img-blog.csdnimg.cn/20200311234514722.png)

日志的具体规范的官方文档： [日志官方文档地址](https://docs.spring.io/spring-boot/docs/2.1.13.RELEASE/reference/html/boot-features-logging.html) 

![](https://img-blog.csdnimg.cn/20200311235229239.png)