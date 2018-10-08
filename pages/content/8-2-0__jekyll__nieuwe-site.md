---
layout   : course
permalink: generators/jekyll/nieuwe-site/
published: false
#
abbreviations:
  - cli
  - computer
hyperlinks:
  - csse
  - education
  - software
title     : Nieuwe site
title_long: Nieuwe Jekyll-site
---
{%- include includes.md %}

We gaan een nieuwe Jekyll-website maken voor [GitHub Pages](https://pages.github.com). De Jekyll-versie die GitHub Pages gebruikt, is niet noodzakelijk de allerlaatste, daarom gebruiken we [Bundler][] om een specifieke versie te installeren en te gebruiken.

Rootmap
-------

Ga naar de map `Code` met de alias `c` en maak een nieuwe map aan met `mkdir`.

{% highlight posh %}
PS> c
PS> mkdir 1718-nmd2-code-jekyll
PS> c 1718-nmd2-code-jekyll
{% endhighlight %}

> Mappen & Bestanden
> ---
> - ~/Code/
>   -  1718-nmd2-code-jekyll/
{:.card.card-tree}

Nieuwe voorbeeldsite
--------------------

Ga naar de map met de alias `c` en open de nieuwe site in [Visual Studio Code][].

{% highlight posh %}
PS> c 1718-nmd2-code-jekyll
PS> code .
{% endhighlight %}

### Installatie

> Zie ook
> ---
> - [Bundler][]
> - [Gemfile](http://bundler.io/gemfile.html)
{:.card.card-link}

Jekyll is in de programmeertaal [Ruby][] geschreven, maar er zijn ook nog extra **Ruby Gems** (packages) nodig om de Jekyll-site te draaien. Die Gems gaan we met [Bundler][] installeren.

Maak een nieuw bestand `Gemfile` (**hoofdlettergevoelig!**).

> Folders & Files
> ---
> - 1718-nmd2-code-jekyll/
>   - Gemfile
{:.card.card-tree}

In het bestand voegen we de bron van de Ruby Gems (`source`) en de Ruby Gem `github-pages` die we willen installeren, waarin o.a. ook de Ruby Gem `jekyll` zit. Voor Windows is er ook nog een extra Ruby Gem `wdm` nodig, die we enkel gaan installeren op het Windows-platform (`if Gem.win_platform?`), dus niet op bijvoorbeeld macOS.

{% highlight rb linenos %}
source 'http://rubygems.org'
gem 'github-pages'
gem 'wdm', '>= 0.1.1' if Gem.win_platform?
{% endhighlight %}{:data-file="~/Code/1718-nmd2-code-jekyll/Gemfile"}

Installeer de Ruby Gems uit de `Gemfile` met [Bundler][].

{% highlight posh %}
PS> c 1718-nmd2-code-jekyll
PS> bundle install
{% endhighlight %}

Na de installatie wordt een nieuw bestand gemaakt `Gemfile.lock` waarin ook de geïnstalleerde versienummers bewaard worden.

> Folders & Files
> ---
> - 1718-nmd2-code-jekyll/
>   - Gemfile
>   - Gemfile.lock
{:.card.card-tree}

Je kan de Ruby Gems ook updaten met Bundler.

{% highlight posh %}
PS> bundle update
{% endhighlight %}

### Opzetten van een site

> Zie ook
> ---
> - [Jekyll Configuration](http://jekyllrb.com/docs/configuration/)
{:.card.card-link}

Maak een nieuw, leeg bestand `_config.yml` aan, met de opdracht `touch` of met de teksteditor (`code`).

{% highlight posh %}
PS> c 1718-nmd2-code-jekyll
PS> touch _config.yml
PS> code .
{% endhighlight %}

Dit bestand gaan we later aanvullen.

> Mappen & Bestanden
> ---
> - 1718-nmd2-code-jekyll/
>   - _config.yml
>   - Gemfile
>   - Gemfile.lock
{:.card.card-tree}

### De site bouwen

Op dit ogenblik hebben we enkel nog maar een leeg bestand `index.html` dat we gaan aanvullen.

{% highlight html linenos %}
{% include_relative _code/jekyll/nieuwe-site/index.00.html %}
{% endhighlight %}{:data-file="index.html"}

Nu kunnen we de site gaan bouwen.

{% highlight posh %}
PS> c 1718-nmd2-code-jekyll
PS> bundle exec jekyll build
{% endhighlight %}

Jekyll genereert de website in de map `_site`. Dit is de **rootmap** van de website.

> Opgelet
> ---
> **Verander niks** in de map `_site`. Deze map wordt door Jekyll gegenereerd, alle wijzigingen zullen verloren gaan!
{:.card.card-warning}

> Mappen & Bestanden
> ---
> - 1718-nmd2-code-jekyll/
>   - _site/
>     - Gemfile
>     - Gemfile.lock
>     - index.html
>   - _config.yml
>   - Gemfile
>   - Gemfile.lock
>   - index.html
{:.card.card-tree}

De bestanden `Gemfile` en `Gemfile.lock` worden ook in de rootmap gekopieerd terwijl dit niet de bedoeling is, want die maken geen deel uit van de statische site. Alle mappen en bestanden die niet beginnen met een '_' worden naar de rootmap gekopieerd.

We gaan dit oplossen door `_config.yml` aan te passen.

{% highlight yml linenos %}
{% include_relative _code/jekyll/nieuwe-site/_config.00.yml %}
{% endhighlight %}{:data-file="_config.yml"}

{% highlight posh %}
PS> bundle exec jekyll build
{% endhighlight %}

> Mappen & Bestanden
> ---
> - 1718-nmd2-code-jekyll/
>   - _site/
>     - index.html
>   - _config.yml
>   - Gemfile
>   - Gemfile.lock
>   - index.html
{:.card.card-tree}

In het huidige voorbeeld heeft het weinig zin om een SSG te gebruiken, want het bestand wordt enkel gekopieerd en niet verwerkt.

We kunnen bijvoorbeeld op de pagina het tijdstip van genereren tonen door de variabele `site.time` met behulp van [Liquid][] te tonen (`{% raw %}{{ site.time }}{% endraw %}`). In de gegenereerde pagina wordt de code dan vervangen door het echte tijdstip.

#### Front Matter

Je zegt aan Jekyll dat en document moet worden door bovenaan het document **[Front Matter](http://jekyllrb.com/docs/frontmatter/)** toe te voegen. Front Matter begint en eindigt met `---` (drie koppeltekens), waartussen optioneel ook extra gegevens in de vorm van [YAML][] toegevoegd kunnen worden.

{% highlight html linenos %}
{% include_relative _code/jekyll/nieuwe-site/index.01.html %}
{% endhighlight %}{:data-file="index.html"}

We kunnen het gegenereerde tijdstip nog wat verfijnen door er een [Liquid][] **filter** op toe te passen. Jekyll heeft een aantal [uitbreidingen op de standaard filters](https://jekyllrb.com/docs/templates/), waaronder `date_to_long_string`.

{% highlight html linenos %}
{% include_relative _code/jekyll/nieuwe-site/index.02.html %}
{% endhighlight %}{:data-file="index.html"}

### Lokale server

Websites draaien eigenlijk op een HTTP-server. Jekyll heeft een ingebouwde server die je kan starten.

#### Server starten

Door de ingebouwde server van Jekyll te starten wordt de site ook gebouwd.

{% highlight posh %}
PS> c 1718-nmd2-code-jekyll
PS> bundle exec jekyll serve
{% endhighlight %}

Van zodra de website gebouwd is, kan je de website openen met de getoonde URI. In ons geval is dit (waarschijnlijk) <http://127.0.0.1:4000/1718-nmd2-code-jekyll/>.

Jekyll start ook automatisch een **watcher** die de bestanden in de gaten houdt en telkens als er een wijziging vastgesteld wordt, voert Jekyll een nieuwe **build** uit.

#### Server stoppen

Stop de server met <kbd class="keyboard"><kbd>Ctrl</kbd>+<kbd>C</kbd></kbd>.

Jekyll Helpfunctie
------------------

{% highlight posh %}
PS> c 1718-nmd2-code-jekyll
PS> bundle exec jekyll help
{% endhighlight %}