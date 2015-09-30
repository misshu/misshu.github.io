---
layout: post
title: 简单的纯CSS下拉菜单
date: 2015-09-30 21:39
author: misshu
comments: true
categories: front-end
---
实际运行效果：

<div class="nav">
   <ul>
    <li><a href="#">技术</a>
     <ul>
	     <li><a href="#">linux</a></li>
		 <li><a href="#">javascript</a></li>
		 <li><a href="#">html</a></li>
		 <li><a href="#">css</a></li>
		 <li><a href="#">c++</a></li>
	 </ul>
  </li>
  <li><a href="#">工作</a></li>
  <li><a href="#">生活</a>
      <ul>
	     <li><a href="#">旅游</a></li>
		 <li><a href="#">锻炼</a></li>
		 <li><a href="#">美食</a></li>
	 </ul>
  </li>
  <li><a href="#">歌曲</a></li>
 </ul>
</div>
	 
<style>
body{
  font-size:16px;
  margin:0px;
  padding:0px;
}
li{
  list-style:none;
}
.nav{
  width:720px;
  height:50px;
  margin:0 auto;
}
.post li a{
  width:100px;
  text-decoration:none;
  background-color:#eee;
  color:#000;
  display:block;
}
.post li a:hover{
  background-color:#666;
  color:#fff;
}
.post ul li{
  float:left;
  text-align:center;
  line-height:40px;
  position:relative;
}
li ul{
  position:absolute;
  border-bottom:2px solid #fff;
  display:none;
}
.post ul li ul li{
  float:none;
  width:100px;
  margin-left:-40px;
  border-bottom:2px solid #fff;
}
 li:hover ul{
  display:block;
}
</style>


HTML 部分代码：

{% highlight html %}
<div class="nav">
  <ul>
   <li><a href="#">技术</a>
     <ul>
	<li><a href="#">linux</a></li>
	<li><a href="#">javascript</a></li>
        <li><a href="#">html</a></li>
	<li><a href="#">css</a></li>
	<li><a href="#">c++</a></li>
     </ul>
  </li>
  <li><a href="#">工作</a></li>
  <li><a href="#">生活</a>
     <ul>
	<li><a href="#">旅游</a></li>
	<li><a href="#">锻炼</a></li>
	<li><a href="#">美食</a></li>
	 </ul>
  </li>
  <li><a href="#">歌曲</a></li>
  </ul>
</div>
{% endhighlight %}

CSS 部分代码啊；

{% highlight css %}
ul li{
  float:left;
  text-align:center;
  line-height:40px;
  position:relative;
}
li ul{
  position:absolute;
  border-bottom:2px solid #fff;
  display:none;
}
ul li ul li{
  float:none;
  width:100px;
  margin-left:-40px;
  border-bottom:2px solid #fff;
}
 li:hover ul{
  display:block;
}
{% endhighlight %}