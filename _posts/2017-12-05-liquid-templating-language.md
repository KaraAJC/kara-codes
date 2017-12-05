---
layout: post
title: Liquid Gold -The Liquid Templating Language
date:  2017-12-05
categories: til
tags: Liquid Templating Shopify Jekyll
permalink: /til/liquid-templating-language
---

Today, there was a lot going on, and though I wanted to go in a thousand directions, I tackled a little thing I've been wanting to with this blog, and pulled down the theme layout to get it where I wanted. This involved working with a bit of **Liquid**

Liquid is a templating language that [Jekyll](https://jekyllrb.com/docs/templates/) uses, and it lets you create dynamic code inside HTML that will evaluate before rendering onto the page with the info you'd like seen.

This gave me the ability to display the post's tags above, and write a conditional for the lovely bottom links on my posts, so folks can go check out the other posts I've written, without having to go back to the TIL page.

Here's a snippet of what liquid code looks like:
![carbon code snippet image of liquid templating](/pics/liquid-snippet.png)

{% raw %}
<pre>
Here's a way to write code snippets: HOW META!

  {% highlight ruby %} <-- here's an expression to be evaluated
    def print_hi(name)
      puts "Hi, #{name}"
    end
    print_hi('Kara')
    #=> prints 'Hi, Kara' to STDOUT.
  {% endhighlight %} <-- This ends that statement

Here's how the date is being rendered on this page:

  datetime="{{ page.date | date_to_xmlschema }}" <-- this was in HTML
  {% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}
  {{ page.date | date: date_format }} <-- Here's where a pipe is being used
    to set extra formatting to the info that's being rendered
</pre>
{% endraw %}

Today, I learned that [Shopify](https://github.com/Shopify) maintains Liquid, and you can find out more info on their [github repository](https://github.com/Shopify/liquid).

Now that you're at the bottom of this post, won't you enjoy another TIL using the links below?! 👋