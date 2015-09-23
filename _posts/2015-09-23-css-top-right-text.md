---
layout: post
title: css制作斜角文字
date: 2015-09-23 18:18
author: misshu
comments: true
categories: [未分类]
---
在很多网站里面都可以看到“独播”、“限时抢购”、“自制”等文字制作位于图片或者div元素的右上角。本文将揭开其面纱。

实际运行结果：
<img src="http://7xmcf2.com1.z0.glb.clouddn.com/css-z.png" alt="" />

制作图片的斜角装饰文字与div元素的斜角装饰文字的原理差不多，所以具体实现一种即可。

HTML代码：

{% highlight html %}
<div class="pic">
    <img src="z.jpg"/>
	<span class="tf">独播</span>
</div>
{% endhighlight %}

css代码：

{% highlight css %}
 body{
	position:relative;
}
.pic{
	position:absolute;
	left:40%;
	top:100px;
	overflow:hidden;
}
.pic img{
	position:relative;
}
.tf{
	position:absolute;
	top:10px;
	left:75%;
	width:100px;
	height:30px;
	text-align:center;
	display:block;
	overflow:hidden;
	line-height:30px;
	font-weight:300;
	color:#fff;
	background-color:#f60;
	transform:rotate(45deg);
}
{% endhighlight %}
