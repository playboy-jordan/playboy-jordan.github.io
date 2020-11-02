---
layout: post
title:  springboot的自动装配原理
category: springboot
excerpt: "本文主要介绍springboot自动装配原理"
---
上一篇博客中，我们知道了springboot是通过META-INF/spring.factories来自动为我们导入第三方架包的。下面是spring.factories中页面， 

![](https://img-blog.csdnimg.cn/2020030223101139.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

从图中，我们可以看到这里面有很多的第三方架包，那假如我们就启动一个小小的Helloworld.它也会给我们自动启用这些全部架包吗？我们先随便看一个架包文件。答案就揭晓了。 

![](https://img-blog.csdnimg.cn/20200302232115406.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

另外，我们还可以通过prefix.value来改变配置的值。 

![](https://img-blog.csdnimg.cn/20200302232548580.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/20200302232653967.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

由此，我们可以得出来，配置文件中其他配置项也是某某文件中prefix+value来的。 下图是@contional拓展注解的图片  

![](https://img-blog.csdnimg.cn/20200302233709137.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

那我们有办法直接看到那些开启？那些禁用了吗？ 我们可以直接在application.properties中配置debug=true 

![](https://img-blog.csdnimg.cn/20200302234140819.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

接着，我们去控制台看看： Positive matches下面都是开启，Negative matches:下面的都是不开启的。 

![](https://img-blog.csdnimg.cn/20200302234321431.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/20200302234357685.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

