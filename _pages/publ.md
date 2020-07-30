---
layout: single
title: "P"
permalink: /publications/
---

> <a href="https://scholar.google.com/citations?user=FLWcEXMAAAAJ&hl=en">Google Scholar page</a>

> <a href="https://arxiv.org/a/joshi_a_4.html">arXiv author's page</a>

> <a href="https://orcid.org/0000-0002-0890-2389">ORCID page</a>

{% assign p = site.publications %}
{% assign p_sorted = p | sort: "date_of_entry" | reverse %}
{% assign p_newest = p_sorted | first %}

<h1 class="mt-4">List of Publications</h1>
<p class="page__meta">Updated on {{ p_first.date_of_entry | date_to_long_string }}</p>

A list of publications is also available on my google scholar page above. 

{% assign pp = site.publications | where_exp: "item","item.type == 'preprint'" %}
{% assign pp_size = pp | size %}
{% if pp_size > 0 %}
{% assign pp_sorted = pp | sort: "date_of_entry" | reverse %}
<h2 class="mt-4">Preprints</h2>
{% for pub in pp_sorted %}
<div class="pubitem">
  <div class="pubtitle">
    {{ pub.title }}
  </div>
  <div class="pubauthors">
    {{ pub.authors }}
  </div>
  <div class="pubinfo">
    {{ pub.forum }}, {{ pub.year}}
  </div>
  <div class="publinks">
  &#8226; <a href="{{pub.doi}}"> DOI </a>&nbsp;&nbsp; &#8226; <a href="{{pub.arxiv}}">arXiV</a>
    &nbsp;&nbsp; &#8226; <a href="{{pub.url | relative_url }}">Citation and Abstract</a>
  </div>
</div>
{% endfor %}
{% endif %}

{% assign jp = site.publications | where_exp: "item","item.type == 'journal'" %}
{% assign jp_size = jp | size %}
{% if jp_size > 0 %}
{% assign jp_sorted = jp | sort: "date_of_entry" | reverse %}
<h2 class="mt-4">Journal Publications</h2>
{% for pub in jp_sorted %}
<div class="pubitem">
  <div class="pubtitle">
    {{ pub.title }}
  </div>
  <div class="pubauthors">
    {{ pub.authors }}
  </div>
  <div class="pubinfo">
    {{ pub.forum }}, {{ pub.year}}
  </div>
  <div class="publinks">
  &#8226; <a href="{{pub.doi}}"> DOI </a>&nbsp;&nbsp; &#8226; <a href="{{pub.arxiv}}">arXiV</a>
    &nbsp;&nbsp; &#8226; <a href="{{pub.url | relative_url }}">Citation and Abstract</a>
  </div>
</div>
{% endfor %}
{% endif %}

{% assign cp = site.publications | where_exp: "item","item.type == 'conf'" %}
{% assign cp_size = cp | size %}
{% if cp_size > 0 %}
{% assign cp_sorted = cp | sort: "date_of_entry" | reverse %}
<h2 class="mt-4">Conference Publications</h2>
{% for pub in cp_sorted %}
<div class="pubitem">
  <div class="pubtitle">
    {{ pub.title }}
  </div>
  <div class="pubauthors">
    {{ pub.authors }}
  </div>
  <div class="pubinfo">
    {{ pub.forum }}, {{ pub.year}}
  </div>
  <div class="publinks">
  &#8226; <a href="{{pub.doi}}"> DOI </a>&nbsp;&nbsp; &#8226; <a href="{{pub.arxiv}}">arXiV</a>
    &nbsp;&nbsp; &#8226; <a href="{{pub.url | relative_url }}">Citation and Abstract</a>
  </div>
</div>
{% endfor %}
{% endif %}
