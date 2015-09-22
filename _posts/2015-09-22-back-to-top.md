---
layout: post
title:  返回顶部
date: 2015-09-22 22:50 +0800
author: misshu
categories: front-end
---


时间对于现在的人来说时间很宝贵，我们甚至不愿多花一秒钟在无聊的事情、或者是无聊的动作上。当你在浏览一个网站底部想快速返回顶部的时候，一直滑动鼠标就会觉得特别麻烦特别累。一般的网页下方都会放置一个返回顶部按钮，尤其是页面顶部没有导航的网页。

返回顶部有三种方法可以是实现。一种是很变态的方法就是直接放一个链接，属性直接写 `href="#"`；直接一点击就可以返回顶部了，但是有个缺点就是这个按钮不能隐藏。第二种就是要用到 JavaScript。隐藏按钮就要监听滚动事件，用 JavaScript 就要考虑到兼容。第三种就是封装得很完美的 jQuery。

简单写一个滚动到顶部的函数，但还需要一个判断滚动多少才显示按钮。

`document.documentElement.clientHeight` 这是一个浏览器界面的高度，也就是说网页的可视大小，并不是一滚动就会显示出隐藏的按钮而是要滚动一屏才会显示。如果想要一滚动就会显示出隐藏的按钮把这段代码替换成0，当它大于0时就会显示。

JavaScript 方法代码：

{% highlight javascript %}
	  var clientHeight = document.documentElement.clientHeight;

	  var backToTop = document.getElementById('backtotop');

	  var windowScrolltop = document.documentElement.scrollTop || document.body.scrollTop;

	  function toggleToTop(){

	    var windowScrolltop = document.documentElement.scrollTop || document.body.scrollTop;

		if(windowScrolltop > clientHeight){

		  backToTop.classList.add('show');

		}else{

		  backToTop.classList.remove('show');

		}

		}

		function scrollToTop(){

		  window.scrollTo(0,0);
          
		}
		if(document.addEventListener){

		  backToTop.addEventListener('click',scrollToTop,false);

		}else{

		  backToTop.attachEvent('onclick',scrollToTop);

		};

		if(document.addEventListener){

		  document.addEventListener('scroll',toggleToTop,false);

		}else{

		  document.attachEvent('scroll',toggleToTop);

		}
{% endhighlight %}

jQuery方法代码：

{% highlight javascript %}
$(document).ready(function($){
    $('#backtotop').click(function(){
        $('html,body').animate({scrollTop:0},1000);
        return false;
    })
})
{% endhighlight %}

HTML代码:

{% highlight html %}
   <div id="backtotop" class="show">^</div>
{% endhighlight %}