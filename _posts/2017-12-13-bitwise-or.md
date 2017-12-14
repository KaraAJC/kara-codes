---
layout: post
title: Bitwise OR
date:  2017-12-13
categories: til
tags: base bitwise ruby
permalink: /til/bitwise-or
---

Talking to a senior engineer the other day, I came across a line of code that looked something like this:

```ruby
items.inject(0) { |perm, v| ( v | items[i].even? ) }
```
(_PS this is gibberish ruby code I made up, don't at me._)

When I looked at the line, I thought, _OH, ruby uses pipe?!... is that what's going on?_

And that's when I learned about **Bitwise OR**.

## Bitwise OR

In ruby, we know OR operator to look like `||`. when you see `|` you're looking at a _Bitwise_ OR operator, and what it's comparing, is a value, **bit by bit**.

If we looked at a more simple example, we can walk through bitwise comparison step by step:
```ruby
# want to know a number's binary representation?
# use to_s and give a base as the arguement
12.to_s(2) #=> "1100"
9.to_s(2) #=> "1001"

# so, if we wanted to compare the binary representations of 12 and 9, the bitwise or operator will look at each bit (from right to left) and choose 1 if one or both bits are 1:

"1 1 0 0"
"1 0 0 1"
---------
 1 1 0 1 # guess what number this is?

```

## bhet, WHY?!

In the example I was reviewing with the senior engineer, we were looking at code dealing with permissions, which represented them as long, binary numbers to show whether a given person had the permission, er nah.

Another use case that keeps coming up is "flags" that represent
state based on several conditions...

An interesting case I'd love to dive into someday is how it's used to deal with colors, getting RGB values, and the like...

If you deal with a complicated set of IF THIS THEN THAT conditionals, maybe bitwise is worth using!

## Resources

- Fascinating resource on Bitwise Operators: [Ruby's Bitwise Operators by Calle Erlandsson](https://www.calleerlandsson.com/rubys-bitwise-operators/)
- Visual tutorial of Bitwise Operators, language agnostic, with useful practical applications of each: [Understanding Bitwise Operators](https://code.tutsplus.com/articles/understanding-bitwise-operators--active-11301)
- Stack Overflow thread of folks giving examples for when they've used Bitwise operators in real life!: [Real world use cases of bitwise operators](https://stackoverflow.com/questions/2096916/real-world-use-cases-of-bitwise-operators)