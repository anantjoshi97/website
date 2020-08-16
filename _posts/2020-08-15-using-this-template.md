---
layout: single
tag: technical-writing
title: "Using This Template"
date: 2020-08-16 21:34:00 +0530
last_modified_at: 2020-08-17 21:34:00 +0530
---

This website is based on the <a href="https://github.com/mmistakes/minimal-mistakes">Mininal Mistakes</a> theme.

## Configuration

* Change personal details in ```_config.yml```.
* Change (or remove) the google analytics code in ```_includes/head.html```.

## Layouts

### Single

For documentation on using the single layout, refer to the <a href="https://mmistakes.github.io/minimal-mistakes/docs/layouts/#single-layout">documentation</a> of the original theme.

I have added an additional paramater, ``` title_in_header``` for any file which uses the single layout, the default value for which is ```false``` and can be set to
```true``` as per requirement. This variable is supposed to be used if an overlay image in the header is used.
If it is set to ```true```, the title of the page will be displayed in the overlay image, otherwise, it will be displayed below the overlay image in style ```<h1>```. 
Since pages do not use an overlay image by default, its default value is set to ```false```.

### Pubpage

For each publication, add a markdown file under the ```/publications``` directory and use the ```pubpage``` layout. Front matter variables for this layout have been listed below in the code snippet. 

{% highlight yaml %}
---
layout: pubpage 
title: "Title of publication in quotes." #Markdown syntax allowable. Mathmode does not work.
authors:  "Authors in quotes"
type: type_of_publication #conf (for conference), journal, preprint
forum:  "Place of publication" #for conf and journal
year: "Month and Year of Publication" #for conf and journal. for journal, add volume as well. 
doi: doi_link #without quotes
arxiv: arxiv_link #without quotes
date_of_entry: date #when this publication was added to your website, used for indexing purposes
---
{% endhighlight %}

After the front matter, add the abstract under after giving a heading ```## Abstract ``` using markdown or ```<h2 id="abstract"> Abstract </h2> ``` using html, and the citation below it, using code highlighting, with the heading ```## Citation ``` using markdown or ```<h2 id="citation"> Citation </h2> ``` using html.

The displayed output, on the Publications page, (for ```conf``` and ```journal```) will be

<blockquote>
<div class="pubitem" id="pubdisplay">
  <div class="pubtitle">
    Title
  </div>
  <div class="pubauthors">
    Authors
  </div>
  <div class="pubinfo">
    Forum, Year  
  </div>  
  <div class="publinks">
  &#8226; <a href="#pubdisplay"> DOI </a>&nbsp;&nbsp; &#8226; <a href="#pubdisplay">arXiV</a>
    &nbsp;&nbsp; &#8226; <a href="#pubdisplay">Citation and Abstract</a>
  </div>
</div>
</blockquote>

For ```preprint``` the fields not used will not be displayed. The citation and abstract hyperlink will lead to a project page which contains the citation and abstract for
```conf``` and ```journal```, and only the abstract for ```preprint```.

<div class="notice">
  Hyperlinks have been disabled in this example of displayed output, and will point back to the example. 
</div>


## Using hyperlinks

* For external links, use either the ``` <a href> ``` command in html or ```[Link text](link) ``` syntax in markdown.
* For an internal link to a different page with permalink ```/page/```, use ``` <a href="{{ '/page/' | relative_url }}"> ``` or ``` <a href="{{ '/page/#section' | relative_url }}"> ``` to reference a section on that page, and ``` <a href="#abstract"> ``` for same linking to a section on the same page. For more on referencing see this <a href="https://stackoverflow.com/questions/6695439/how-to-link-to-a-named-anchor-in-multimarkdown">answer</a> on stackoverflow. For details on using permalinks look <a href="https://jekyllrb.com/docs/permalinks/"> here</a>.

## Colours and Fonts

* For hyperlink styling and decoration, make changes in ```  website/_sass/minimal-mistakes/_base.scss  ```.
* For changing colours and font size, make changes in ```  website/_sass/minimal-mistakes/_variables.scss  ```.
* To use mathmode, (```mathjs``` has been enabled in the head file, ```_includes/head.html```), encase text in ``` $$ ... $$ ```.

## Grouping of Posts

* For the more technically or scholastically oriented posts, use the tag ``` technical-writing ``` in the page front matter.
For posts which are narratives, use the tag ``` narrative ```.
* For printing a list of posts using <a href="https://jekyllrb.com/docs/liquid/filters/">liquid filters</a>, use the following code snippets as guidelines:

{% highlight html %}
{% raw %}
<!-- List of all posts-->
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

<!-- Posts by year -->
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


<!-- Posts by year and month -->
{% assign postsByYear = site.posts | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
<h1>{{ year.name }}</h1>
{% assign postsByMonth = year.items | group_by_exp:"post", "post.date | date: '%B'" %}
{% for month in postsByMonth %}
<h2>{{ month.name }}</h2>
{% assign postsByDate = month.items | sort:"date" | reverse %}
<ul>
  {% for post in postsByDate %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }} - {{ post.date | date_to_long_string }} </a>      
    </li>
  {% endfor %}
</ul>
{% endfor %}
{% endfor %}



<!-- Posts by specific tag and year -->
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


<!-- Posts by tag and year-->
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

<!-- Posts by specific collection -->
<h1>TW</h1>
{% for post in site.technical-posts %}
<ul>
  <li><a href="{{ post.url }}">{{ post.title }}</a></li>
</ul>
{% endfor %}

<!-- Posts by collection -->
{% for collection in site.collections %}
{% assign name = collection.label %}
  <h1>{{ name }}</h1>
  {% for post in site.[name] %}
  <ul>
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  </ul>
  {% endfor %}
{% endfor %}
{% endraw %}
{% endhighlight %}


