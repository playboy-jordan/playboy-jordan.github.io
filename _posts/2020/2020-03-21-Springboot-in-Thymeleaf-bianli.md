---
layout: post
title:  Springboot中Thymeleaf简单遍历
category: springboot
excerpt: "本文主要介绍springboot中使用Thymeleaf遍历数据"
---
首先，我们建立一个实体类

```
package com.example.demo.entity;

public class Product {
	
	  private String name;
	  private int price;
	  private int inStock;
	  
	  
	public Product() {
		super();
	}
	public Product(String name, int i, int inStock) {
		super();
		this.name = name;
		this.price = i;
		this.inStock = inStock;
	}
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public int getPrice() {
		return price;
	}
	public void setPrice(int price) {
		this.price = price;
	}
	public int getInStock() {
		return inStock;
	}
	public void setInStock(int inStock) {
		this.inStock = inStock;
	}
	  
	  

}


```

然后我们在controller里面放值 

```
package com.example.demo.controller;

import java.util.*;
import java.util.Map;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.ResponseBody;

import com.example.demo.entity.Product;

@Controller
public class BootController {
          
	         @RequestMapping("/welcome")
	         public String welcome(Map<String,Object> map) {
	        	
	         List<Product> prods=new ArrayList<>();
	         prods.add(new Product("a",100,10));
	         prods.add(new Product("b",200,20));
	         prods.add(new Product("c",300,30));
	         
	         map.put("prods", prods);
	        	 return "result";
	         }  
	         
}


```

因为是初次使用，我们去thymeleaf官网复制实例代码 

![](https://img-blog.csdnimg.cn/20200320225024727.png)

![](https://img-blog.csdnimg.cn/20200320225131942.png)

```
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
            <div th:each="prod : ${prods}">
            <h3 th:text="${prod.name}">Onions</h3>
            <h3 th:text="${prod.price}">2.41</h3>
           
            </div>
</body>
</html>

```

效果如图所示 

![](https://img-blog.csdnimg.cn/20200320225235511.png)

