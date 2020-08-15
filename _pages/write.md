---
title: "Scribbles"
permalink: /writing/
layout: single
sidebar:
  nav: posts
author_profile: false
tagline: "Tagline custom"
excerpt: "Excerpt custom"  
header:
  overlay_image: /assets/images/unsplash-image-1.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
  image_description: "Image Description Custom"
  show_overlay_excerpt: true
title_in_header: true
#entries_layout: grid
#show_excerpts: false # true (default), false
---

This page contains a list of all my 'scribbles', some derived from experience I have had with various events in my life, and some more technically oriented. To see a list of only the more technically oriented posts, visit this <a href="{{ '/twriting/' | relative_url }}"> page </a>. 
For only those posts which contain narratives of my experiences visit this <a href="{{ '/nwriting/' | relative_url }}"> page </a>. 

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

<!-- Posts by year and month -->
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
     {{ post.date | date: "%B %-d, %Y" }} | <a href="{{ post.url | relative_url }}">{{ post.title }}</a>      
    </li>
  {% endfor %}
</ul>
{% endfor %}
{% endfor %}



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

<!-- Posts by specific collection 
<h1>TW</h1>
{% for post in site.technical-posts %}
<ul>
  <li><a href="{{ post.url }}">{{ post.title }}</a></li>
</ul>
{% endfor %}
-->


<!-- List of all posts
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
-->
