---
layout: single
---

## Layouts

### Single

https://mmistakes.github.io/minimal-mistakes/docs/layouts/#single-layout

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

<div class="pubitem">
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
  &#8226; <a href="doi_link"> DOI </a>&nbsp;&nbsp; &#8226; <a href="arxiv_link">arXiV</a>
    &nbsp;&nbsp; &#8226; <a href="publication_page">Citation and Abstract</a>
  </div>
</div>

For ```preprint``` the fields not used will not be displayed. The citation and abstract hyperlink will lead to a project page which contains the citation and abstract for
```conf``` and ```journal```, and only the abstract for ```preprint```.

## Using hyperlinks

* For external links, use either the ``` <a href> ``` command in html or ```[Link text](link) ``` syntax in markdown.
* For internal links, use ``` <a href="{{ '/writing/' | relative_url }}"> ``` or ``` <a href="{{ '/writing/#section' | relative_url }}"> ``` for the same page, and ``` <a href="#abstract"> ``` for same page links.

For details on using permalinks look here https://jekyllrb.com/docs/permalinks/

## Colours

hyperlink decoration

colours

looping over tags, collections

page front matter - various options

config - personal details, SEO,

## Mathmode

change google analytics from head

pubpage layout
