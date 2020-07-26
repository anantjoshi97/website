---
title: "Posts by Year"
permalink: /writing/
layout: single
author_profile: true
#entries_layout: grid
#show_excerpts: false # true (default), false
---

Hello

<!--
{% assign postsByYear = site.posts | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
<h1>{{ year.name }}</h1>
<ul>
  {% for post in year.items %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}-{{ post.date | date_to_long_string }}</a>
    </li>
  {% endfor %}
</ul>
{% endfor %}
-->


<!--
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
-->
