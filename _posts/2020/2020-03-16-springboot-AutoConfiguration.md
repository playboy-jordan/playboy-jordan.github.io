---
layout: post
title:  Springboot中WebMvcAutoConfiguration源码的解读
category: springboot
excerpt: "本文主要介绍springboot中AutoConfiguration的解读"
---
开头，我们先来看下在springboot中如何整一个欢迎页。在我们之前学的web项目中，都是在xml中配置欢迎页面，但是我们在sprginboot中该如何配置呢？ 我们可以顺着WebMvcAutoConfiguration看看 

![](https://img-blog.csdnimg.cn/20200316204222982.png)

![](https://img-blog.csdnimg.cn/20200316204457924.png)

![](https://img-blog.csdnimg.cn/20200316205011155.png)

![](https://img-blog.csdnimg.cn/20200316205027205.png)

那我们有办法自定义静态文件的位置吗？ 我们可以看看源码 

![](https://img-blog.csdnimg.cn/20200316213816227.png)

![](https://img-blog.csdnimg.cn/20200316213831266.png)

![](https://img-blog.csdnimg.cn/20200316213847504.png)

根据上面的源码，我们可以知道，我们可以通过 Properties文件中的 prefix+属性来自定义 

![](https://img-blog.csdnimg.cn/20200316214500528.png)

![](https://img-blog.csdnimg.cn/20200316214516802.png)

![](https://img-blog.csdnimg.cn/20200316214559376.png)

