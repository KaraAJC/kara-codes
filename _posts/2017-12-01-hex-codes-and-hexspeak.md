---
layout: post
title: The HexQueen Taught Me Her Spells
date:  2017-12-01
categories: til technical
tags: basecs hex number magic 0xQU33N
permalink: /til/hex-codes-and-hexspeak
---

I'm a pretty avid podcast listener, and one of my recent favorites are bringing [Vaidehi Joshi](https://twitter.com/vaidehijoshi)'s [blog series `base.cs`](https://medium.com/basecs)to life, with another fave of mine, [CodeNewbie](https://www.codenewbie.org/)'s [Saron Yitbarek](https://twitter.com/saronyitbarek). It's called the [`base.cs podcast`](https://www.codenewbie.org/basecs), and on Episode 3, Saron and Vaidehi talked about Hexes.

### These hexes aren't what you may be thinking about...
![miss celie puts a hex on em](https://media.giphy.com/media/12gGSEDF4uyuis/giphy.gif)

In this case, we're talking about a Hexadecimal number, or a `Base16` number.

What I learned from this podcast specifically was about the magical numbers `8`, `16`, and `256`, which makes conversion between `bits`, `bytes`, and `hex` codes perfect, 🍰 _scrumptious even!_ 🍰

Additionally, as developers began using hex codes in their work, they created a set of codes that could universally mean something, and these codes are called `HexSpeak`.

I found a list of HexSpeak terms and here are a few of my favorite:

```js
0x8BADF00D - BADFOOD
0xC00010FF - COOLOFF
0xDEADC0DE - DEADCODE
```
```css
SPOILER ALERT: This is a CSS code.. based in HexSpeak
#BADA55 - BADASS!
```

_(I actually got that last one from [@wesbos](https://twitter.com/wesbos))_

In [base.cs Episode 4](https://www.codenewbie.org/basecs), they talked over how Hexadecimals are used to define colors, and how to translate them out, so the above hexcode `#BADA55` is actually `rgb(186,218,85)`.
Here's how that's calculated:

```ruby
# NOTE this is pseudocode!

r=0xBA, g=0xDA, b=0x55

A.to_denary = 10 # Perfect A!
B.to_denary = 11

# B is in what we'd think of as the "tens" place,
# so we multiply that number by 16
11 * 16 = 176

# We then add "A" to the value from B,
# and get r's value, 186! WOO WOO
176 + 10 = 186

-----
# RGB's B value may seem like it should just be 55,
# but we're actually looking at 0x55, a hexadecimal number,
# so let's see how we translate that into denary:

5.to_denary = 5
5.to_denary = 5

# Again, we have the first five in the "tens" place:
5 * 16 = 80

# Then we add the second five:
80 + 5 = 85

```

Here's a cool site to check out hexspeak/leetspeak color codes at [BADA55.io](http://bada55.io/alpha) so you can color with [`#C0FFEE`](http://bada55.io/c0ffee), and other cool words...

And if you want to read more in-depth about hexcodes, check out Vaidehi's Basecs post on the subject:

- [Hexes and other Magical Numbers](https://medium.com/basecs/hexs-and-other-magical-numbers-9785bc26b7ee)

Amazing work, Vaidehi & Saron! you are both indeed `#BADA55`, Perfect `0x`**A**'s!!
