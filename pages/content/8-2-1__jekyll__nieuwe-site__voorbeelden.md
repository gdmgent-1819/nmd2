---
layout   : course
permalink: generators/jekyll/nieuwe-site/voorbeeldsites/
published: false
#
abbreviations:
  - cli
  - computer
hyperlinks:
  - csse
  - education
  - software
title     : Voorbeelden
title_long: Voorbeeldsites
---
{%- include includes.md %}

Jekyll kan zelf een voorbeeldsite genereren. In de meeste gevallen ben je beter af met volledig zelf gebouwde site, maar als demonstratie van de mogelijkheden is het wel interessant.

Een blanco voorbeeldsite
------------------------

> Opgelet
> ---
> **Niet toepassen!** Dit is enkel een voorbeeld.
{:.card.card-warning}

Maak eerst een map, de `Gemfile` en installeer met [Bundler][].

{% highlight posh %}
PS> bundle exec jekyll new . --blank --force
{% endhighlight %}

> Mappen & Bestanden
> ---
> - jekyll-blank/
>   - _drafts/
>   - _layouts/
>   - _posts/
>   - Gemfile
>   - Gemfile.lock
>   - index.html
{:.card.card-tree}

Een uitgebreide voorbeeldsite
-----------------------------

> Opgelet
> ---
> **Niet toepassen!** Dit is enkel een voorbeeld.
{:.card.card-warning}

Maak eerst een map, de `Gemfile` en installeer met [Bundler][].

{% highlight posh %}
PS> bundle exec jekyll new . --force
{% endhighlight %}

> Mappen & Bestanden
> ---
> - jekyll-demo/
>   - _posts/
>     - 2017-11-06-welcome-to-jekyll.markdown
>   - _config.yml
>   - .gitignore
>   - 404.html
>   - about.md
>   - Gemfile
>   - Gemfile.lock
>   - index.md
{:.card.card-tree}
