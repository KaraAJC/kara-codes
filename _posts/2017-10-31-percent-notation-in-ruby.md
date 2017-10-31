---
layout: post
title: percent notation in ruby
date:   2017-10-31 04:30:30 -0500
categories: til
tags: ruby syntax array rubocop
permalink: /til/percent-notation-in-ruby
---

In creating a CLI bank challenge for my SheNomads Mentorship program, I found out about a RuboCop error surrounding the use of Array Literals, when referring to an Array of Words.

Apparently, there's 'Percent Notation', [which is preferred to the literal array syntax](https://github.com/bbatsov/ruby-style-guide#percent-w), as mentioned in Batssov's Ruby-Style-Guide, the source of RuboCop's preferences. When you use Array literal you get this warning:
```ruby
'Use `%w` or `%W` for array of words'
```

[Percent Notation](https://en.wikibooks.org/wiki/Ruby_Programming/Syntax/Literals#The_.25_Notation) lets you "stringify" a set of characters, separated and returned as a certain object, depending on the modifier.

{% highlight ruby %}
# using Array literal syntax:
['January', 'February', 'June', 'July'].include?('September') #=> false

# using % notation:
%w[January February June July].include?('September') #=> false
{% endhighlight %}

There was an interesting discussion on the topic, over at the [`RuboCop` github repo](https://github.com/bbatsov/ruby-style-guide/issues/526), and the person who authored the issue [had a lot of thoughts about it](https://www.chrisrolle.com/blog/ruby-percentage-notations), that helped to clarify it's use.