---
layout: post
title:  springboot中多环境设置及切换
category: springboot
excerpt: "本文主要介绍springboot中环境切换"
---
springboot默认只会读取application.properties里面配置的端口号，假如我们有多个环境，我们可以在application.properties中指定：spring.profiles.active=环境名 

![](https://img-blog.csdnimg.cn/20200306235447613.png)

![](https://img-blog.csdnimg.cn/20200306235459828.png)

上面是在application.properties中配置多环境。下面，我们来看下怎么在yaml中配置多环境； 

![](https://img-blog.csdnimg.cn/20200307000214115.png)

上面两种情况都是把我们要设置的环境给写死，下面我们看下如何动态设置环境 第一种方法是通过通过运行参数指定环境，在STS(Eclipse) ：Run Configuration - Argument - program Argument 使用 –spring.profiles.active=环境名 

![](https://img-blog.csdnimg.cn/20200307000809634.png)

![](https://img-blog.csdnimg.cn/20200307000846468.png)

第二种方法是通过vm参数指定环境，在STS(Eclipse) ：Run Configuration - Argument - VM中使用 -Dspring.profiles.active=环境名，其中D是虚拟机需要的一个参数 

![](https://img-blog.csdnimg.cn/20200307001555537.png)

![](https://img-blog.csdnimg.cn/20200307001513287.png)

第三种方法是我们在dos窗口中通过命令来指定 首先，我们在dos窗口中通过打包命令：mvn clean package -DskipTests=true来打包，然后在target目录中打开dos窗口然后运行命令java -jar 项目名.jar --spring.profiles.active=环境名 就可以动态的指定环境。 

![](https://img-blog.csdnimg.cn/20200307002719185.png)

![](https://img-blog.csdnimg.cn/20200307002804734.png)

