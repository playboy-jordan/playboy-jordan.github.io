---
layout: post
title:  测试自动化部署5
category: html
excerpt: "本文主要介绍html中head标签"
---
1、 **网页标题标签** 

```
<title>HTML学习</title><!--网页标题标签:告诉浏览器使用什么标题显示网页-->
```

2、 **编码格式标签** 

```
<!--<meta  charset="utf-8"/>--><!--网页解析编码格式配置(HTML5):告诉浏览器使用指定的编码格式解析文档-->
   <meta http-equiv="content-type" content="text/html;charset=utf-8"/><!--HTML4:文档编码格式设置-->	
```

3、**网页搜索优化标签** 

```
<!--
   了解:
		关键字
		网页描述
		作者
	   作用:提升网页在浏览器中的搜索概率.
	-->
	<meta name="keywords" content="HTML,SXT,张老师,506"/><!--网页关键字-->
	<meta name="description" content="本网页上是关于HTML的head标签学习的,特别棒,6666."/><!--网页描述-->
	<meta name="author" content="张老师"/><!--网页作者-->
```

4、**网页指定跳转标签** 

```
<meta  http-equiv="refresh" content="5;url=http://www.baidu.com"/><!--网页自动跳转-->
```

5、 **其他标签**
css的引入标签和js引入标签

6、**示例代码**

```
<html>
	<head>
		<!--head标签中主要配置浏览器的配置信息-->
		<title>HTML学习</title><!--网页标题标签:告诉浏览器使用什么标题显示网页-->
		<!--<meta  charset="utf-8"/>--><!--网页解析编码格式配置(HTML5):告诉浏览器使用指定的编码格式解析文档-->
		<meta http-equiv="content-type" content="text/html;charset=utf-8"/><!--HTML4:文档编码格式设置-->


		<!--
			了解:
				关键字
				网页描述
				作者
			作用:提升网页在浏览器中的搜索概率.
		-->
		<meta name="keywords" content="HTML,SXT,张老师,506"/><!--网页关键字-->
		<meta name="description" content="本网页上是关于HTML的head标签学习的,特别棒,6666."/><!--网页描述-->
		<meta name="author" content="张老师"/><!--网页作者-->
		<meta  http-equiv="refresh" content="5;url=http://www.baidu.com"/><!--网页自动跳转-->
	</head>
	<body>
		this is my first html
	</body>
</html>
```

