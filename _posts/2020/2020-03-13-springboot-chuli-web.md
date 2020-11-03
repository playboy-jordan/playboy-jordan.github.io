---
layout: post
title:  Springboot处理Web静态资源
category: springboot
excerpt: "本文主要介绍springboot如何处理静态资源"
---
首先，我们要新建一个web项目，可以按照new - spring starer -设置（选择 需要的场景，web）步骤来新建。下面是图示: 首先使用快捷键 ctrl+n 出来新建页面，然后输入spring，选择spring Starter Project ,然后next 

![](https://img-blog.csdnimg.cn/20200312203927883.png)

![](https://img-blog.csdnimg.cn/20200312204304462.png)

![](https://img-blog.csdnimg.cn/20200312204710857.png)

创建项目的过程可能需要等一会儿，耐心点就好了。 

![](https://img-blog.csdnimg.cn/20200312205529396.png)

我们新建一个controller，然后在里面写一些简单的代码来测试下 

![](https://img-blog.csdnimg.cn/20200312213454640.png)

![](https://img-blog.csdnimg.cn/20200312213635558.png)

spring boot是一个jar，因此 静态资源就不是再存放到 webapps中， 存放在哪里？ 静态资源的存放路径已经被WebMvcAutoConfiguration类通过addResourceHandlers()指定:/webjars/ 我们可以通过以下路径找到对应的源码: 

![](https://img-blog.csdnimg.cn/2020031221532993.png)

![](https://img-blog.csdnimg.cn/20200312215346567.png)

![](https://img-blog.csdnimg.cn/20200312215539677.png)

那该如何理解WebJar呢？ webjar其实就是把我们以前引用的一些.js文件给变成架包了，然后我们引用架包就跟以前引用那些.js文件一样的效果。 

![](https://img-blog.csdnimg.cn/20200312220036909.png)

​	也可以直接点击[webjar地址](https://www.webjars.org/) 进去。 下图是进去的首页 

![](https://img-blog.csdnimg.cn/20200312220331442.png)

![](https://img-blog.csdnimg.cn/20200312221029250.png)

以前我们引入jquery，需要引入.js文件，但是现在我们只需要引入对应的依赖就行了 

![](https://img-blog.csdnimg.cn/20200312221803148.png)

![](https://img-blog.csdnimg.cn/20200312222134687.png)

![](https://img-blog.csdnimg.cn/20200312222348689.png)

现在js文件进来是进来了，但是我们该如何引入呢？ 答案是从Jar目录结构的webjars开始写 比如我们要访问下图中的文件: 

![](https://img-blog.csdnimg.cn/20200312222928127.png)

![](https://img-blog.csdnimg.cn/20200312223237863.png)

那么假如是我们自己写的静态资源该怎么访问呢？ 有两个办法，一个就是我们写出来，打成jar，然后再引进来，这种方法显然台麻烦，还有第二种方法就是springboot给我们准备了几个地方，我们只需要直接放就可以啦，具体那几个地方， 我们可以去源码里面看看 

![](https://img-blog.csdnimg.cn/20200312225817983.png)

![](https://img-blog.csdnimg.cn/2020031222594568.png)

我们可以 上面的四个地方放置我们自己写静态资源， 

![](https://img-blog.csdnimg.cn/20200312230804689.png)

![](https://img-blog.csdnimg.cn/20200312230927532.png)

