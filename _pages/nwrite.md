---
title: "Narrative Writing"
permalink: /nwriting/
layout: single
sidebar:
  nav: posts
#author_profile: true
#entries_layout: grid
#show_excerpts: false # true (default), false
---

This page contains a list of all my narrative posts.
<!-- Posts by year and month 
{% assign postsByYear = site.posts | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
<h2>{{ year.name }}</h2>
{% assign postsByMonth = year.items | group_by_exp:"post", "post.date | date: '%B'" %}
{% for month in postsByMonth %}
<h3>{{ month.name }}</h3>
{% assign postsByDate = month.items | sort:"date" | reverse %}
<ul>
  {% for post in postsByDate %}
    <li>
     {{ post.date | date_to_long_string }} | <a href="{{ post.url | relative_url }}">{{ post.title }}</a>      
    </li>
  {% endfor %}
</ul>
{% endfor %}
{% endfor %}
-->

{% assign postsByYear = site.tags.narrative-writing | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
<h2>{{ year.name }}</h2>
{% assign postsByMonth = year.items | group_by_exp:"post", "post.date | date: '%B'" %}
{% for month in postsByMonth %}
<h3>{{ month.name }}</h3>
{% assign postsByDate = month.items | sort:"date" | reverse %}
<ul>
  {% for post in postsByDate %}
    <li>
     {{ post.date | date_to_long_string }} | <a href="{{ post.url | relative_url }}">{{ post.title }}</a>      
    </li>
  {% endfor %}
</ul>
{% endfor %}
{% endfor %}


<!-- Posts by tag and year
{% for tag in site.tags %}
{% assign name = tag[0] %}
<h1>{{ name }}</h1>
{% assign postsByYear = tag[1] | group_by_exp:"post", "post.date | date: '%Y'" %}
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
{% endfor %}
-->
