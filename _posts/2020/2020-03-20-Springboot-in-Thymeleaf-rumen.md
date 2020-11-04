---
layout: post
title:  Springboot中Thymeleaf入门
category: springboot
excerpt: "本文主要介绍springboot中使用Thymeleaf"
---
在Springboot中，默认是不支持jsp的，官网比较推荐模板引擎thymeleaf。
如何理解模板引擎呢？请看下图

![](https://img-blog.csdnimg.cn/20200318205127917.png)

那我们该如何引入thymeleaf呢？ 

![](https://img-blog.csdnimg.cn/20200318210328127.png)

![](https://img-blog.csdnimg.cn/20200318210403947.png)

![](https://img-blog.csdnimg.cn/20200318210707336.png)

![](https://img-blog.csdnimg.cn/20200318231248384.png)

我们现在是引入thymeleaf 了，但是我们开发的时候在哪儿写代码呢？ 我们可以去源码里面看下 

![](https://img-blog.csdnimg.cn/20200319233048190.png)

![](https://img-blog.csdnimg.cn/20200319233139511.png)

由源码我们可以知道，只要我们在类路径的一个叫templates的文件夹中创建.html文件就可以啦。 我们先在templates中新建一个html页面 

![](https://img-blog.csdnimg.cn/20200319234826989.png)

然后去Thymeleaf官网看下基本的语法 Thymeleaf官网地址为:[thymeleaf官网](https://www.thymeleaf.org/) 

![](https://img-blog.csdnimg.cn/20200319235219583.png)

![](https://img-blog.csdnimg.cn/20200319235420730.png)

![](https://img-blog.csdnimg.cn/20200319235937364.png)

我们先随意复制下官网的代码来学习。 模板引擎其实就是前段准备好模板，然后在后端赋值，然后在前段显示出来 

![](https://img-blog.csdnimg.cn/20200320001110361.png)

![](https://img-blog.csdnimg.cn/20200320001205978.png)

![](https://img-blog.csdnimg.cn/20200320001246478.png)

th语法不仅可以改变text里面的值，还可以改变id, class值 

![](https://img-blog.csdnimg.cn/20200320002000368.png)

![](https://img-blog.csdnimg.cn/20200320002057846.png)

