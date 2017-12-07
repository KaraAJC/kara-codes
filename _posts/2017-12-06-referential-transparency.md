---
layout: post
title: Referential Transparency
date:  2017-12-06
categories: til
tags: FP Functions Map Filter
permalink: /til/referential-transparency
---

Today we were lucky to have Bill Schofield from Pivotal Labs speak to the cohort about Functional Programming, and believe you me, I was taking notes!

Instead of going over all the pieces discussed, I updated a presentation slide deck with the following tenets of Functional Programming vs Object Oriented Programming:

![FP vs OOP](/pics/FP-vs-OOP.png)

<br/>

One particular tenet I learned about today was **Referential Transparency**.

According to a super useful article about the subject:

> Referential transparency means that a function call can be replaced by its value or another referentially transparent call with the same result.

So what does that look like?

{% highlight javascript %}
  // taking the following example:
  const findBigNums = (arr) => arr.filter(num => num > 3);

  // num > 3 is an evaluation that, if put into it's own function
  const isABigNum = (num) => num > 3;

  //... and can replace the evaluation and can get the same result.
  const findBigNums = (arr) => arr.filter(num => isABigNum(num));

  //... even if the implementation of how you get to that result differs
  const isABigNum = (num) => [3,4,5...1000].include(num);
{% endhighlight %}

To learn more about the origin of the term `Referential Transparency`, check out this article [Why do they call it Referentially Transparent?](http://www.nobugs.org/blog/archives/2008/11/12/why-do-they-call-it-referentially-transparent/)
Here are some other articles I found useful:
- [What is Referential Transparency?](https://www.sitepoint.com/what-is-referential-transparency)
- [Four Principles of Object Oriented Programming](https://anampiu.github.io/blog/OOP-principles/)
- [First-class and Higher Order Functions: Effective Functional JavaScript](https://hackernoon.com/effective-functional-javascript-first-class-and-higher-order-functions-713fde8df50a)
