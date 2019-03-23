---
layout: page
title: Learns
permalink: /til/
---

`#SoakingUpThatKnowledge`

## Stuff I 💖 learning about:
 - Emoji 🤓
 - Hex Codes
 - Apps that QTPOC folks are making
 - Hackathons
 - Linux Commands
 - Naming Conventions
 - Ways to be more inclusive
 - A11y implementations

## TIL posts:
<ul>
{% for post in site.categories['til'] %}
  <li>
    {{ post.date | date_to_string }} |
    <a href="{{ post.url | absolute_url }}">
      {{ post.title }}
    </a>

  </li>
{% endfor %}
</ul>
