---
layout: single
title: "P"
permalink: /publications/
---

L o P

<h1 class="mt-4">Publications</h1>
{% assign jp = site.publications | where_exp:"item","item.type == journal"}
<!-- {% assign publications = jp | sort: "date_of_entry" | reverse %} -->
{% for pub in jp %}
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
  &#8226; <a href="{{pub.doi}}"> DOI </a>&nbsp;&nbsp; &#9679; <a href="{{pub.arxiv}}">arXiV</a>
    &nbsp;&nbsp; &#9679; <a href="{{pub.url | relative_url }}">Citation and Abstract</a>
  </div>
</div>

{% endfor %}
