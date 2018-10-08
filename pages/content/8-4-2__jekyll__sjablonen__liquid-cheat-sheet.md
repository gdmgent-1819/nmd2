---
layout   : course
permalink: generators/jekyll/sjablonen/liquid-cheat-sheet/
published: false
#
title     : Liquid
title_long: Liquid Cheat Sheet
---

Tags
----

### Commentaar

{% highlight liquid %}{% raw %}
{% assign «variabelenaam» = «expressie» %}
{{ «variabelenaam» }}
{% endraw %}{% endhighlight %}


### Variable Tags

 - `assign`{:.k}

{% highlight liquid %}{% raw %}
{% assign «variabelenaam» = «expressie» %}
{{ «variabelenaam» }}
{% endraw %}{% endhighlight %}

 - `capture`{:.k}

{% highlight liquid %}{% raw %}
{% capture «variabelenaam» %}«inhoud»{% endcapture %}
{{ «variabelenaam» }}
{% endraw %}{% endhighlight %}

### Flow Control
 
 - `if` `endif`
 - `if` `else` `endif`
 - `if` `elsif` `else` `endif`
 - `unless` `endunless`
 - `unless` `else` `endunless`
 - `unless` `elsif` `else` `endunless`
 - `case` `when` `else` `endcase`

### Lussen

 - `for` `in` `endfor`

{% highlight liquid %}{% raw %}
{% for «item» in («begingetal»..«eindgetal») %}
  {{ «item» }}
{% endfor %}
{% endraw %}{% endhighlight %}

{% highlight liquid %}{% raw %}
{% for «item» in «array» %}
  {{ «item» }}
{% endfor %}
{% endraw %}{% endhighlight %}

{% highlight liquid %}{% raw %}
{% for «item» in «array» reversed %}
  {{ «item» }}
{% endfor %}
{% endraw %}{% endhighlight %}

{% highlight liquid %}{% raw %}
{% for «item» in «array» limit:«getal» offset:«getal» %}
  {{ «item» }}
{% endfor %}
{% endraw %}{% endhighlight %}

Objects
-------

Het `forloop`{:.k}-object bestaat binnen een `{% raw %}{% for %}{% endraw %}`-lus.

 - `forloop.length`{:.k}
 - `forloop.first`{:.k}
 - `forloop.index`{:.k}
 - `forloop.index0`{:.k}
 - `forloop.rindex`{:.k}
 - `forloop.rindex0`{:.k}
 - `forloop.last`{:.k}

Filters
-------

###  Array Filters

{% highlight liquid %}{% raw %}
{{ «arrayvariable» | «filter» }}
{% endraw %}{% endhighlight %}

 - `size`{:.k}
 - `first`{:.k}
 - `index`{:.k}
 - `last`{:.k}
 - `map`{:.k}
 - `sort`{:.k}
 - `sort:`{:.k} `'«eigenschap»'`{:.v}
 - `join`{:.k}  
   cf. `split`{:.k} bij String Filters
 - `reverse`{:.k}

### String Filters

{% highlight liquid linenos %}{% raw %}
{% assign «stringvariable» = '«tekenstring»' %}
{{ «stringvariable» | «filter» }}
{% endraw %}{% endhighlight %}

#### Letterkast

 - `capitalize`{:.k}  
   {{ 'LOREM IPSUM.' | capitalize }}
   {{ 'lorem ipsum.' | capitalize }}  
 - `downcase`{:.k}  
   {{ 'LOREM IPSUM.' | downcase }}
 - `upcase`{:.k}  
   {{ 'lorem ipsum.' | upcase }}

#### Toevoegen

 - `prepend:`{:.k} `'«tekenstring»'`{:.v} voor
 - `append:`{:.k} `'«tekenstring»'`{:.v} achter

#### Verwijderen

 - `remove:`{:.k} `'«tekenstring»'`{:.v} alle
 - `remove_first:`{:.k} `'«tekenstring»'`{:.v} eerste

#### Vervangen

 - `replace:`{:.k} `'«tekenstring»'`{:.v} alle
 - `replace_first:`{:.k} `'«tekenstring»'`{:.v} eerste

#### Uitsnijden

- `slice:`{:.k} `«startindex»`{:.v}
- `slice:`{:.k} `«startindex»,`{:.v} `«eindindex»`{:.v}

#### Afkappen

 - `truncate:`{:.k} `«maximaal-aantal-tekens»`{:.v}  
   {{ 'lorem ipsum sid dolor amet.' | truncate: 9 }}
 - `truncatewords:`{:.k} `«maximaal-aantal-woorden»`{:.v}  
   {{ 'lorem ipsum sid dolor amet.' | truncatewords: 3 }}

#### Opsplitsen in array

- `split:`{:.k} `'«tekenstring»'`{:.v} cf. `join`{:.k} bij Array Filters

#### Witruimte (spaties en nieuwe regels)

 - `strip`{:.k} links en rechts
   - `lstrip`{:.k} links
   - `rstrip`{:.k} rechts
 - `strip_newlines`{:.k}

- `strip_html`{:.k}  
  verwijdert HTML-elementen.

### Getallen

- `minus:`{:.k} `«getal»`{:.v}
- `plus:`{:.k} `«getal»`{:.v}
- `times:`{:.k} `«getal»`{:.v}
- `divided_by:`{:.k} `«getal»`{:.v}
- `modulo:`{:.k} `«getal»`{:.v}

### URI

- `absolute_url`{:.k}
- `relative_url`{:.k}