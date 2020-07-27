---
title: "Posts by Year"
permalink: /writing/
layout: single
author_profile: true
#entries_layout: grid
#show_excerpts: false # true (default), false
---

Hello

<!-- Posts by year
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

<!-- Posts by specific tag and year 
{% assign postsByYear = site.tags.Post-Formats | group_by_exp:"post", "post.date | date: '%Y'" %}
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

<!-- Posts by collection 
{% for collection in site.collections %}
{% assign name = collection.label %}
  <h1>{{ name }}</h1>
  {% for post in site.[name] %}
  <ul>
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  </ul>
  {% endfor %}
{% endfor %}
-->

<!-- Posts by specific collection -->

<h1>TW</h1>
{% for post in site.technical-posts %}
<ul>
  <li><a href="{{ post.url }}">{{ post.title }}</a></li>
</ul>
{% endfor %}



<!-- List of all posts
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
-->
