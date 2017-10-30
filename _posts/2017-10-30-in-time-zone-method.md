---
layout: post
title: in_time_zone method
date:  Mon Oct 30 08:55:48 CDT 2017
categories: til
tags:  rails DateTime
permalink: /til/in-time-zone-method
---
Today, we're teaching rails, and used an example of gyms and workout classes.

To create a workout class, we needed to have duration times, and wanted to give more info about the DateTime Object.

My colleague Jon let the class know about [`in_time_zone`](https://apidock.com/rails/DateAndTime/Zones/in_time_zone) which is a rails method that lets you pass a TimeZone instance or a string that identifies a time zone as an arguement, and get the simultaneous time in the given time zone.

{% highlight ruby %}
DateTime.utc(2000).in_time_zone('Alaska') # => Fri, 31 Dec 1999 15:00:00 AKST -09:00
{% endhighlight %}