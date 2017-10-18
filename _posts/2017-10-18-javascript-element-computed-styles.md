---
layout: post
title: Javascript Element Computed Styles
categories: til
tags:  js css stack_overflow
permalink: /til/2017-10-18-javascript-element-computed-styles
---
Today, in an effort to try to publish my first answer on Stack Overflow, I found a newly asked question about Javascript and I was in! I pulled down the HTML they listed as using, and tried to replicate the problem, and kept coming up short with this line of code:

{% highlight javascript %}
  alert(document.getElementById("first").style.top);
{% endhighlight %}

Which led me to the docs about how `element.style` actually works.
