---
layout: post
title:  第一个SpringBoot程序及执行原理
category: springboot
excerpt: "本文主要介绍第一个微服务小demo"
---
第一，我们需要把jdk和maven安装好，并且配置好他们对应的环境变量。 第二，我们需要准备工具，准备工具的话，我们可以直接在eclipes中通过marketplace来安装sts插件，但是这种方法非常考验网速，如果网速不够给力，经常会安装失败。那sts插件的作用是啥呢？它的作用就是我们在abc.xml(代指.xml类文件，下文也是如此)的时候可以给我们一定的提示，否则我们写abc.xml的时候，需要纯手敲。当然，还有一种方法就是我们直接安装一个叫做sts的软件，这个软件其实就是一个自带sts插件的eclipse。 

[sts软件的下载地址]: https://spring.io/tools

![](https://img-blog.csdnimg.cn/20200220230243225.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

到这个页面之后，我们选择对应的版本，然后直接下载就可以啦。 下载好之后是一个.jar文件，我们可以把它解压，解压之后的画面是下面这样子的。 

![](https://img-blog.csdnimg.cn/20200220231756660.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

然后我们把contents.zip文件再解压，会看到下面的画面： 

![](https://img-blog.csdnimg.cn/20200220232058964.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

我们点击那个SpringToolSuite4.exe文件就可以启动sts软件了。 因为我们是第一次打开软件，所以我们需要设置下字体和配置下maven，注意maven需要配置两个地方，一个是Installations，另一个是User Settings。 接下来，我们先去spring官网下载一个小的现成的test来感受下springboot。 首先，我们打开spring的官网，然后在Projects下面选择springboot，如下图所示: 

![](https://img-blog.csdnimg.cn/20200220235022990.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

接着拉到最下面，我们会看到一个Quick start，然后我们点击 Spring Initializr 

![](https://img-blog.csdnimg.cn/20200220235240239.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

就会进入到下面的页面。 

![](https://img-blog.csdnimg.cn/20200220235803571.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

然后点击下图的箭头中的地方，就可以生成一个基本的springboot的小example。 

![](https://img-blog.csdnimg.cn/20200221000039357.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

下载之后，如下图所示 

![](https://img-blog.csdnimg.cn/20200221231441915.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

我们把这个zip文件解压缩，然后import进sts软件。 

![](https://img-blog.csdnimg.cn/20200221231917693.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

导入进去之后，我们通过执行那个文件来运行这个项目，当我们看到那个图案和springboot字样及其版本号的时候，就表示这个springboot项目运行成功了。 下图是各个目录的作用： 

![](https://img-blog.csdnimg.cn/20200221233143727.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

以前，我们写web程序的时候，通常需要在webcontent里面建立web.xml文件并且最后还要把项目打成war包发布到tomcat中。但我们现在springboot中写web程序，上面那些都不需要。 我们新建一个controller并且写下如下代码， 

![](https://img-blog.csdnimg.cn/20200221235648977.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

然后再去DemoApplication中启动项目，最后在浏览器地址栏输入http://localhost:8080/helloWorld 可以得到如下图所示： 

![](https://img-blog.csdnimg.cn/20200221235509139.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

可见，我们写好项目之后不需要部署到tomcat就可以运行了，这是因为springboot中内置了tomcat，并且不需要达成war包再执行，可以直接执行。 接下来，我们来看下application.properties中可以干啥？ 第一：可以配置tomcat的端口号，如下图： 

![](https://img-blog.csdnimg.cn/20200222000333517.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/20200222000418986.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

安装下图的提示，我们可以进入到springboot的版本制裁中心 

![](https://img-blog.csdnimg.cn/20200224230452725.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/2020022423050666.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

到了版本制裁中心，我们往下拉，可以看到如下图所示的好多版本 

![](https://img-blog.csdnimg.cn/20200224230732981.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

springboot为啥在pom.xml中给了我们这么多的版本呢？ 原来，这是为了版本的冲突，比如，我们要开发一个功能，在开发这个功能的过程中，我们需要用到三个架包，如果我们选择的版本不够合适，就出现由于版本冲突而造成的问题。这就是版本制裁中心存在的意义。所以我们在需要引入一个依赖的时候，不需要写版本号。 在pom.xml中，我们还可以看到 spring-boot-starter-web，这是web启动器 

![](https://img-blog.csdnimg.cn/20200224232238194.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

我们按住ctrl，然后鼠标左键点进去就可以看到如下图，很明显，下面是一堆的架包，这些架包是springboot提前为我们准备的。这是因为sprigboot已经将一些框架或第三方应用给设置成了场景start,我们需要哪个只需要引入哪个场景即可。 

![](https://img-blog.csdnimg.cn/20200224232548342.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

那么如果我们需要看其他启动器的话，我们应该怎么看呢？ 第一步，我们打开下面的页面： 

![](https://img-blog.csdnimg.cn/20200224234851572.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

然后，我们稍微往下拉一点点： 点击粉色的那个链接就可以进入到一个目录，如下图： 

![](https://img-blog.csdnimg.cn/20200225215938371.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

再次点击这个starters,我们就饿可以如愿以偿的得到我们想要找的 

![](https://img-blog.csdnimg.cn/20200224235558817.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

下图就是我们所要找的所有的启动器 

![](https://img-blog.csdnimg.cn/20200224235732398.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

接下来，我们从springboot的主配置类开始来简单了解下spingboot的注解 

![](https://img-blog.csdnimg.cn/20200225223537925.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

我们点击进去之后，会看到很多注解，我们目前只要简单看下圈住的这两个注解 

![](https://img-blog.csdnimg.cn/20200225223829947.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

第一个是@SpringBootConfiguration，下图使我们点击去看到的源码，其实根据字面意思，我们也能感觉到这是一个springboot的配置类。 关于@Configuration，有两点需要注意，第一点是只要有这个注解，这个类就是一个配置类。第二点，有这个注解，意味着这个类已经纳入到spring容器的管理之中（在spring中，我们用的是@Component）。 

![](https://img-blog.csdnimg.cn/2020022522484951.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

第二个是@EnableAutoConfiguration，这个注解顾名思义就是自动配置，自动配置的原则就是约定优于配置，类似于我们常用的“老地方见”。 我们点开这个注解进去可以看到如下图： 

![](https://img-blog.csdnimg.cn/20200225230307935.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

我们重点来看看圈中的这两个注解。 第一个是：@AutoConfigurationPackage，这个字面意思就是自动配置包。这个怎么理解呢？对比着spring,我们需要用到那个文件的时候，需要将该文件所在的包配置到配置文件中，但是在springboot中却不需要，就是因为这个注解有自动配置包的作用。 我们点进去@AutoConfigurationPackage，可以看到如下的界面 

![](https://img-blog.csdnimg.cn/20200225231728833.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

然后我们在根据上图点进去Registrar,会会看到下图， 

![](https://img-blog.csdnimg.cn/20200225232040794.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

上图是我打断点截图的，我们可以看到源码是将metadata打成一个包，然后再取包名，就是我们所需要的用的文件的包名–com.example.demo 也可以通过下图验证： 

![](https://img-blog.csdnimg.cn/20200225232432568.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

所以综上所述，@AutoConfigurationPackage的作用是找到@SpringBootApplication所在的类的包，然后将该包及其子包都纳入springn的管理。如果我们用ssm的话，我们需要手动的把控制器（以及其他需要的类）的包手动通过xml文件来配置到scan扫描器(即放到spring容器中)。 接下来，我们来看下@EnableAutoConfiguration中的第二个主要注解：@Import(AutoConfigurationImportSelector.class),这注解我们可以跟第一个主要注解@AutoConfigurationPackage来对比着看，@AutoConfigurationPackage主要是把我们写的代码自动放入到spring容器中管理，而@Import(AutoConfigurationImportSelector.class)主要是把一些第三方依赖给我们自动导入项目中。 

![](https://img-blog.csdnimg.cn/20200302214851434.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

那springboot是如何把那些第三方依赖给我们导入到项目中去的呢？ 原来，在springboot启动的时候，会根据META-INF/spring.factories来找到对应的第三方依赖，并且把这些依赖给导入到项目中去。 按照如下的步骤，我们就可以注解中找到META-INF/spring.factories, 

![](https://img-blog.csdnimg.cn/20200302215708860.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/20200302215721632.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/20200302215924177.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/20200302220510935.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/20200302220718794.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/20200302220836774.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/20200302220919980.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

那我们如何在左边的文件夹中找到这个文件呢？ 

![](https://img-blog.csdnimg.cn/20200302221335710.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/20200302221354535.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDg1MzY2OQ==,size_16,color_FFFFFF,t_70)

