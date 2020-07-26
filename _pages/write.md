---
title: "Posts by Year"
permalink: /writing/
layout: single
author_profile: true
#entries_layout: grid
#show_excerpts: false # true (default), false
---

Hello

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
