---
title: "Technical Writing"
permalink: /twriting/
layout: single
sidebar:
  nav: posts
#author_profile: true
#entries_layout: grid
#show_excerpts: false # true (default), false
---

This page contains a list of all my technically oriented posts. A

{% assign postsByYearToDisplay = site.tags.technical-writing | where_exp:"item", "item.display_post == 'true'" %}
{% assign postsByYear = postsByYearToDisplay.posts | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
<h2>{{ year.name }}</h2>
{% assign postsByMonth = year.items | group_by_exp:"post", "post.date | date: '%B'" %}
{% for month in postsByMonth %}
<h3>{{ month.name }}</h3>
{% assign postsByDate = month.items | sort:"date" | reverse %}
<ul>
  {% for post in postsByDate %}
    <li>
     {{ post.date | date: "%B %-d, %Y" }} | <a href="{{ post.url | relative_url }}">{{ post.title }}</a>      
    </li>
  {% endfor %}
</ul>
{% endfor %}
{% endfor %}



