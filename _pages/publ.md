---
layout: single
title: "P"
permalink: /publications/
---

L o P

<h1 class="mt-4">Publications</h1>

> <a href="https://scholar.google.com/citations?user=FLWcEXMAAAAJ&hl=en">Google Scholar page</a>

> <a href="https://arxiv.org/a/joshi_a_4.html">arXiv author's page</a>

> <a href="https://orcid.org/0000-0002-0890-2389">ORCID page</a>


{% assign jp = site.publications | where_exp: "item","item.type == 'journal'" %}
{% assign jp_size = jp | size %}
{% if jp_size!=0 %}
<script type="text/javascript">
  document.write(jp_size)
</script>
{% assign jp_sorted = jp | sort: "date_of_entry" | reverse %}
{% for pub in publications %}
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
