---
layout   : course
permalink: generators/jekyll/sjablonen/navigatie
published: false
#
abbreviations:
  - computer
  - education
hyperlinks:
  - csse
locals:
  - jekyll
title     : Navigatie
title_long: Voorbeeld van een Navigatie
---
{%- include includes.md %}

Pagina's
--------

Het ingebouwd **object** `site`{:.k} bevat een eigenschap `pages`{:.p} die je kan aanspreken met het `.`. Die eigenschap is een lijst van alle pagina's die website bevat. In programmeertermen heet zo'n lijst een **array**.

Om het voor onszelf overzichtelijk te houden gaan we de array `pages`{:.p} toewijzen (`assign`{:.k}) aan een nieuwe variabele die we de naam `nodes` geven. Een node of een knooppunt is een naam die vaak gebruikt wordt in **contentmanagementsystemen** (CMS'en) voor stukjes inhoud.

> Opmerking
> ---
> Per verwerkt document wordt er al een variabele `page` gemaakt, vandaar dat we de nieuwe variabele een andere naam moeten geven, bijvoorbeeld `node`, maar het mag ook iets anders zijn.
{:.card.card-remark}

Om te kijken wat er in de variable `nodes` kunnen we die tonen met de dubbele accolades, en we passen er ook nog een **filter** `inspect`{:.k} op toe om de inhoud gestructureerder te tonen. We zetten er ook nog een `<pre>`{:.e}-element rond om de inhoud om de oorspronkelijke stuctuur in de browser te tonen.

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/navigatie.00.html %}
{% endhighlight %}{:data-file="navigatie.html"}

De array `nodes` bevat veel meer pagina's dan verwacht. Dat komt omdat Jekyll elk bestand met *Front Matter* als een pagina beschouwt, dus ook SCSS- en CSS-bestanden. We kunnen deze pagina's gaan **filteren**, zodat enkel de echte, gewenste pagina's overblijven.

Zo'n *echte* pagina heeft een eigenschap `layout`{:.p} en de pagina's die we willen overhouden hebben bovendien de layout `default` waarop we kunnen filteren met de filter `where`{:.k}

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/navigatie.01.html %}
{% endhighlight %}{:data-file="navigatie.html"}

Je kan verschillende filters na elkaar toepassen. Zo kunnen we een filter `sort`{:.k} toevoegen om op de eigenschap `title`{:.p} van de pagina te sorteren.

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/navigatie.02.html %}
{% endhighlight %}{:data-file="navigatie.html"}

Navigatie Code
--------------

De lijst met pagina's kunnen we omvormen tot een navigatie voor de website.

Met een `for`{:.k}-lus kan je voor elk van die pagina's een stukje code uitvoeren. De `for`{:.k}-lus loopt doorheen de lijst en maakt voor elke pagina een nieuwe variabele `node` telkens een pagina uit de lijst opgehaald wordt.

Elke pagina (`node`) is een object met de eigenschappen `title`{:.p} en `url`{:.p}, respectievelijk de titel en de URI van die pagina.

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/navigatie.03.html %}
{% endhighlight %}{:data-file="navigatie.html"}

Nu kunnen we de code voor de [Bootstrap navigatie](https://getbootstrap.com/docs/4.0/components/navs/#pills) toevoegen. Het `<nav>`{:.e}-element mag niet herhaald worden, dus zetten we het buiten de `for`{:.k}-lus.

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/navigatie.04.html %}
{% endhighlight %}{:data-file="navigatie.html"}

Het `href`{:.a}-attribuut moet de inhoud krijgen van de eigenschap `url`{:.p} en de inhoud van het `<a>`{:.e}-element krijgt de inhoud van de eigenschap `title`{:.p} van het object `node`.

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/navigatie.05.html %}
{% endhighlight %}{:data-file="navigatie.html"}

Relatieve URI's
---------------

De URI's voor paden zijn relatief ten opzichte van de **server root**. Een GitHub-pages website staat meestal in een submap van die *server root,* en de naam van die submap is de naam van de repository. In je lokale ontwikkelomgeving staat de naam van de submap in de variabele `baseurl`{:.k} in het bestand `_config.yml`.

> Opgelet
> ---
> Opgelet De variabele `baseurl`{:.k} in het bestand `_config.yml` moet overeenkomen met de repositorynaam op [GitHub][], wil je problemen vermijden.
{:.card.card-warning}

> Tip
> ---
> Gebruik een Liquid-filter om de URI te maken:
>
> - `relative_url`{:.k}: zet de `baseurl`{:.k} voor het pad.
> - `absolute_url`{:.k}: zet het protocol, de domeinnaam (en eventueel de poort) en de `baseurl`{:.k} voor het pad.
{:.card.card-tip}

{% highlight liquid %}{% raw %}
<link rel="stylesheet" href="{{ 'assets/css/main.css' }}">
<link rel="stylesheet" href="assets/css/main.css">
{% endraw %}{% endhighlight %}

{% highlight liquid %}{% raw %}
<link rel="stylesheet" href="{{ 'assets/css/main.css' | relative_url }}">
<link rel="stylesheet" href="/«baseurl»/assets/css/main.css">
{% endraw %}{% endhighlight %}

{% highlight liquid %}{% raw %}
<link rel="stylesheet" href="{{ 'assets/css/main.css' | absolute_url }}">
<link rel="stylesheet" href="http://«domein»/«baseurl»/assets/css/main.css">
{% endraw %}{% endhighlight %}

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/navigatie.06.html %}
{% endhighlight %}{:data-file="navigatie.html"}

Actieve Pagina aanduiden
------------------------

Een goede navigatie toont de gebruiker ook welk navigatie-item er actief is. De huidige pagina is de pagina die door Jekyll gebouwd wordt, en die moet in de navigatie als actieve pagina aangeduid worden.

 - De **huidige pagina** is het object `page`{:.k}, met een eigenschap `url`{:.p}.
 - Voor elke **pagina in de navigatie** wordt een object `node`{:.v} met een eigenschap `url`{:.p} gemaakt.
 - Als de eigenschap `url`{:.p} van beide objecten overeenkomt, dan is **pagina in de navigatie** de actieve pagina.

We kunnen de inhoud van de eigenschap van beide objecten bekijken door er een `ìnspect`{:.k}-filter op toe te passen in een `<pre>`{:.e}.

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/navigatie.07.html %}
{% endhighlight %}{:data-file="navigatie.html"}

We maken met `assign`{:.k} een variabele `is_active`{:.v} die standaard de waarde `false`{:.k} krijgt bij het begin van elke `for``{:.k}-lus.

Als de eigenschap `url`{:.p} van beide objecten overeenkomt, dan geven we de variabele `is_active`{:.v} de waarde `true`{:.k}.

Als de variabele `is_active`{:.v} de waarde `true`{:.k} heeft, dan voegen we de CSS-klasse `active` (met extra spatie ervoor!) toe aan het `<a>`{:.e}-element

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/navigatie.08.html %}
{% endhighlight %}{:data-file="navigatie.html"}

Witruimte
---------

Elke Liquid-tag of -object zorgt voor een extra lege regel en eventueel ook spaties in de broncode van de webpagina. met een `-` aan de linker en/of rechter kant kan je de **witruimte** (spaties en regels) verwijderen.

{% highlight liquid linenos %}
{% include_relative _code/jekyll/sjablonen/navigatie.09.html %}
{% endhighlight %}{:data-file="navigatie.html"}