---
layout: single
title: "P"
permalink: /publications/
---

L o P

.pubitem {
  margin: 2em 0;
  line-height: 1em;
}

.pubtitle {
  margin-bottom: .5em;
  line-height: 1.2em;
  font-weight: bold;
}

.pubauthors, .pubinfo {
  font-size: 75%;
  margin-bottom: .75em;
}


<h1 class="mt-4">Publications</h1>
{% assign publications = site.publications | sort: "year" | reverse %}
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
</div>
<div class="publinks">
  &#9658 <a href="{{pub.doi}}"> DOI </a>&nbsp;&nbsp;
  &#9658 <a href="{{pub.arxiv}}">arXiV</a>
</div>
{% endfor %}
