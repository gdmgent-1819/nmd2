---
layout   : course
permalink: generators/jekyll/sjablonen/
published: false
#
abbreviations:
  - computer
  - education
hyperlinks:
  - csse
locals:
  - jekyll
title     : Sjablonen
title_long: Sjablonen met Liquid
---
{%- include includes.md %}

Liquid is een programmeertaal die ontwikkeld werd door [Shopify](https://www.shopify.com) om **sjablonen** *(Eng.: templates)* te maken voor hun eigen e-commerceplatform.

Liquid kan gebruikt worden sjablonen te maken van documenten in diverse andere talen: HTML, Markdown, CSS, SCSS, JSON, YAML … Jekyll zal de sjablonen verwerken tot de einddocumenten die op de website komen.

Liquid bestaat uit:

 1. **Objecten**;
 2. **Tags**;
 3. **Filters**.

> Opgelet
> ---
> Heel wat online-informatie over Liquid heeft betrekking op de **specifieke implementatie** in Shopify en niet op die van Jekyll.
{:.card.card-warning}

> Zie ook
> ---
> - [Liquid][]
> - [Liquid for Designers](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers)
{:.card.card-link}

Markup
------

Om de Liquid-code te onderscheiden van de andere code (bijv. HTML) in een document, moet er specifieke markup gebruikt worden.

De dubbele **accolades** (`{}`) worden gebruikt voor het **tonen van inhoud** *(Eng.: output).* De accolade met **procentteken** (`%`) worden gebruikt voor **logica** *(Eng.: logic)* en **besturingsstroom** *(Eng.: flow control)*

| Soort  | Begin en einde                                         |
|-------:|--------------------------------------------------------|
| Output | `{% raw %}{{{% endraw %}` en `{% raw %}}}{% endraw %}` |
| Tag    | `{% raw %}{%{% endraw %}` en `{% raw %}%}{% endraw %}` |
{:.table.table--primary}

Variabelen
----------

### Globale Variabelen

> Zie ook
> ---
> - [Jekyll / Variables](http://jekyllrb.com/docs/variables/)
> - [Jekyll / Front Matter](http://jekyllrb.com/docs/frontmatter/)
{:.card.card-link}

Jekyll voorziet een aantal standaardobjecten in Liquid, die *globale variabelen* genoemd worden:

 - [`site`{:.k}][]
 - [`page`{:.k}][]
 - [`layout`{:.k}][]
 - [`content`{:.k}][]
 - [`paginator`{:.k}][]

### Eigen Variabelen

#### Aangepaste Site-variabelen

Deze maakt je in `_config.yml` en vraag je op via `site.«variabelenaam»`{:.v}.

{% highlight yml linenos %}
lipsum: Lorem ipsum sid dolor amet.
{% endhighlight %}{:data-file="_config.yml"}

{% highlight liquid %}{% raw %}
<p>{{ site.lipsum }}</p>
{% endraw %}{% endhighlight %}

#### Aangepaste Page-variabelen

Een Page-variabele maak je in de **Front Matter** van het document.

{% highlight liquid linenos %}{% raw %}
---
lipsum: Lorem ipsum sid dolor amet.
---
{% endraw %}{% endhighlight %}{:data-file="index.html"}

{% highlight liquid %}{% raw %}
<p>{{ page.lipsum }}</p>
{% endraw %}{% endhighlight %}

#### Eigen variabelen toewijzen.

Een variabele kan je maken met de `assign`{:.k}-tag.

 - `{% raw %}{%{% endraw %}` `assign`{:.k} `«variabelenaam»`{:.v} `=` `«waarde»`{:.v} `{% raw %}%}{% endraw %}`

{% highlight liquid %}{% raw %}
{% assign lipsum = 'Lorem ipsum sid dolor amet.' %}
{% endraw %}{% endhighlight %}

Daarna kan je verder in de pagina de variabele gebruiken.

{% highlight liquid %}{% raw %}
<p>{{ lipsum }}</p>
{% endraw %}{% endhighlight %}

Jekyll zal de variabele in Liquid omzetten naar tekst.

{% highlight html %}
<p>Lorem ipsum sid dolor amet.</p>
{% endhighlight %}

Tags
----

> Zie ook
> ---
> - [Jekyll / Templates / Tags](http://jekyllrb.com/docs/templates/#tags)
> - [Liquid / Tags / Control Flow](https://shopify.github.io/liquid/tags/control-flow/)
> - [Liquid / Tags / Iteration](https://shopify.github.io/liquid/tags/iteration/)
> - [Liquid / Tags / Variable](https://shopify.github.io/liquid/tags/variable/)
{:.card.card-link}

### Lussen

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/zoekmachines.00.html %}
{% endhighlight %}{:data-file="zoekmachines.html"}

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/zoekmachines.01.html %}
{% endhighlight %}{:data-file="zoekmachines.html"}

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/zoekmachines.02.html %}
{% endhighlight %}{:data-file="zoekmachines.html"}

### If-else

{% highlight html %}{% raw %}
<nav>
{% for node in site.pages %}
  {% if page.path contains node.url  %}
    <a class="nav-item nav-link active" href="{{ node.url | relative_url }}">{{ node.title }}</a>
  {% else %}
    <a class="nav-item nav-link" href="{{ node.url | relative_url }}">{{ node.title }}</a>
  {% endif %}
{% endfor %}
</nav>
{% endraw %}{% endhighlight %}

In het bovenstaand voorbeeld wordt de CSS-klasse `active` toegevoegd aan het element `<a>`{:.e} als het pad van de huidige pagina (`page`) de URI van de pagina uit de lijst (`node`) bevat.

> Opmerking
> ---
> - De bovenstaande code kan veel efficiënter geschreven worden (met minder herhalingen), maar is hier bewust wat langer gehouden voor de duidelijkheid.
{:.card.card-remark}

Filters
-------

> Zie ook
> ---
> - [Jekyll / Templates / Filters](http://jekyllrb.com/docs/templates/#filters)
> - [Liquid / Filters](https://shopify.github.io/liquid/filters/abs/)
{:.card.card-link}

### Sorteren

- `sort`{:.k}

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/sorteren.00.html %}
{% endhighlight %}{:data-file="sorteren.html"}

- `sort:`{:.k} `'«eigenschap»'`{:.v}

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/sorteren.01.html %}
{% endhighlight %}{:data-file="sorteren.html"}

### Debuggen

Debuggen (fouten in de code opsporen en oplossen) is makkelijker als je  stap voor stap kan nagaan wat er gebeurt in de code. Hiervoor zijn er een aantal Filters beschikbaar waarmee je gedetailleerde informatie over de variabele kan opvragen en naar het scherm wegschrijven. 

#### Debug Filter

{% highlight liquid %}{% raw %}
{% assign mijn-variable = 'x' %}
{{ mijn-variable | debug }}
{% endraw %}{% endhighlight %}

#### Inspect Filter

{% highlight liquid %}{% raw %}
{% assign mijn-variable = 'y' %}
<pre>{{ mijn-variable | inspect }}</pre>
{% endraw %}{% endhighlight %}

> Opmerking
> ---
> Met het HTML-element `<pre>`{:.e} zorg je ervoor dat de output netjes gestructureerd op het scherm getoond wordt.
{:.card.card-remark}