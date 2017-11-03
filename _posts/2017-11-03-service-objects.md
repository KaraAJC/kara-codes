---
layout: post
title: service objects
date:  2017-11-03
categories: til technical
tags: ruby rails service OOP PORO
permalink: /til/service-objects
---

`#TheGoodTheBadTheUgly`

I've learned about Service Objects before, but today it's clicked more, partly because of my colleagues lesson on Service Objects, but also from reading articles on why people create, love, or hate service objects.

I saw this tweet recently, and I knew we'd be covering it at Code Platoon very soon:

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">I&#39;ve given this rant in person, but now it&#39;s finally on the web: Enough With the Service Objects Already! <a href="https://t.co/1tfUpXzCg6">https://t.co/1tfUpXzCg6</a></p>&mdash; Avdi Grimm (@avdi) <a href="https://twitter.com/avdi/status/925020098540265472?ref_src=twsrc%5Etfw">October 30, 2017</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

So [reading through](https://avdi.codes/service-objects/), it reminded me that sometimes our conventions are built to alleviate a problem, but it doesn't get at the root of the problem itself, hence the frustration with the use of Service Objects.

I went on to [read an article](https://hackernoon.com/the-3-tenets-of-service-objects-c936b891b3c2) talking about how folks define a service object:

> A Service Object is a PORO(Plain old Ruby Object), that is meant to decompose business objects into manageable classes and methods. ...a Service Object should have a Single Responsibility, be easily testable and...should return something meaningful.

I can see the use in having a private PORO that allows for the logic for some procedure to be separated from the controller, and modularized.

In a project I was a part of this past year, we implemented an activity feed, and utilized an `Events` object, that helped with the procedural tasks of watching events and creating notifications from it.

Given that this is my only exposure to service objects so far, I've yet to have a definite stance on whether a service object is inherantly good or bad, but I look forward to the lessons!

Todays `#TIL` is more of a `#TBD`.

