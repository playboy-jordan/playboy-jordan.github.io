---
layout: post
title:  springboot中配置文件的位置
category: springboot
excerpt: "本文主要介绍springboot中配置文件的位置"
---
在springboot中默认只认识两个配置文件，一个是properties，一个是yml，对于这两个配置文件，如果不冲突的话，就会互相补充。如果冲突的话，则properties优先级高。
虽然springboot认识这两个配置文件，但是可不是这连个配置文件在哪儿放着都认识的，这两个配置文件只能放在如下这四个地方；
file:项目根目录/config
file:项目根目录
classpath:项目根目录/config
classpath:项目根目录

对于这四个位置，如果某个配置冲突，那优先级从上往下。如果不冲突，则互相补充。

下图是示一个关于文件夹的小常识；

![](https://img-blog.csdnimg.cn/20200309231056542.png)

file:项目根目录/config 的位置如下图所示 

![](https://img-blog.csdnimg.cn/20200309232405478.png)

file:项目根目录 的位置如图所示 

![](https://img-blog.csdnimg.cn/20200309232707979.png)

classpath:项目根目录/config的位置如图所示 

![](https://img-blog.csdnimg.cn/20200309233137641.png)

classpath:项目根目录的位置如图所示 

![](https://img-blog.csdnimg.cn/20200309233444357.png)

