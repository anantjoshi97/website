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
* For an internal link to a different page with permalink ```/page/```, use ``` <a href="{{ '/page/' | relative_url }}"> ``` or ``` <a href="{{ '/page/#section' | relative_url }}"> ``` to reference a section on that page, and ``` <a href="#abstract"> ``` for same linking to a section on the same page. For more on referencing see this <a href="https://stackoverflow.com/questions/6695439/how-to-link-to-a-named-anchor-in-multimarkdown"> answer</a> on stackoverflow. For details on using permalinks look <a href="https://jekyllrb.com/docs/permalinks/"> here</a>.

## Colours and Fonts

hyperlink decoration

colours

looping over tags, collections

page front matter - various options

config - personal details, SEO,

## Mathmode

change google analytics from head

pubpage layout
