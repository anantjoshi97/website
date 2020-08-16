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

{% highlight yaml %}
---
layout: pubpage #single
title: "Modification of Hilbert's Space-Filling Curve to Avoid Obstacles: A Robotic Path-Planning Strategy"
authors:  Anant A. Joshi, Maulik C. Bhatt, Arpita Sinha
type: conf
forum:  Sixth Indian Control Conference (ICC)
year: December, 2019
doi: https://doi.org/10.1109/ICC47138.2019.9123166
arxiv: https://arxiv.org/abs/1910.03210
date_of_entry: 2020-07-30 22:54:30 +0530
---
{% endhighlight %}

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

change google analytics from head

pubpage layout
