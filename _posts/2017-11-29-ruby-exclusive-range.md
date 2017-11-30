---
layout: post
title: Ruby's elusive, exclusive Range
date:  2017-11-29
categories: til
tags: ruby range syntax
permalink: /til/ruby-exclusive-range
---

Sometimes, exclusivity is useful, and today, I was reminded of one of those times.

When using a set of ranges to set a case statement, you can use the `Range` class' shorthand for the `#exclude_end?` method. This method allows you to set a range upto, but EXCLUDING the last value as seen here:
```ruby
(1..5).to_a   #=> [1, 2, 3, 4, 5]
(1...5).to_a  #=> [1, 2, 3, 4]
```

So knowing that, you can make a nice method like this, that's clean and understandable:
```ruby

def letter_grade(num_grade)
  case num_grade
  when >= 90
    'A'
  when 80...90
    'B'
  when 70...80
    'C'
  when 60...70
    'D'
  when < 60
    'F'
  else
    "Uhoh.. you can't grade that"
  end
end
```

**Interesting Cases:**

Reading up on the `Range` class, you can do a lot of cool things with one, but the methods that are most interesting are those with different behaviors, depending on if you're using an inclusive, or exclusive range:
```ruby

(1..5).max          #=> 5
(1...5).max         #=> 4

(1..5).last         #=> 5
(1...5).last        #=> 5 (I was surprised by this...)

(1..5).last(2)      #=> [4, 5]
(1...5).last(2)     #=> [3, 4] (...ESPECIALLY this!)

(1..5).size         #=> 5 (note, size only return num on int ranges)
(1...5).size        #=> 4

(1..5).member?(5)   #=> true
(1...5).member?(5)  #=> false
(NO MEMBERS JACKET FOR YOU...5!)

```
So there you have it!

The moral of the story is, be inclusive, until you need to be exclusive!