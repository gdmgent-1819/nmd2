---
layout   : course
permalink: jekyll/installatie/
published: false
#
abbreviations:
  - computer
hyperlinks:
  - csse
  - education
  - software
title     : Installatie
title_long: Installatie van Jekyll
---
{%- include includes.md %}

Wat hebben we nodig?
--------------------

 1. [Dotfiles][];
 2. [Ruby][];
 3. [Bundler][].

Installatie
-----------

### gdm.gent Dotfiles

[*&nbsp;*{:.fas.fa-fw.fa-download}Dotfiles][]{:.button.button--outline.button--primary}

### Ruby

[Ruby][] is een programmeertaal. Samen met Ruby wordt **Gem** geïnstalleerd, waarmee je [Ruby Gems](https://rubygems.org) (Ruby-programma's) kan installeren.

Installeer [Ruby][] met **gdm.gent Dotfiles**.

{% highlight posh %}
PS> InstallRuby
{% endhighlight %}

### Bundler

Ruby Gems kunnen afhankelijk zijn van andere Ruby Gems. Die Ruby Gems noemen we **afhankelijkheden** *(Eng.: dependencies).* Omdat Ruby Gems globaal geïnstalleerd worden en niet per project kan dit problemen geven als verschillende Ruby Gems eenzelfde afhankelijkheid hebben die van versie verschilt.

Om deze afhankelijkheden makkelijker te beheren is er de Ruby Gem [Bundler][]. De afhankelijkheden worden in een bestand `Gemfile` beschreven en de gebruikte **afhankelijkheden en hun versie** worden in een bestand `Gemfile.lock` bewaard.

Installeer [Bundler][] met **gdm.gent Dotfiles**.

{% highlight posh %}
PS> InstallBundler
{% endhighlight %}

> Opmerking
> ---
> `InstallBundler` is eigenlijk niet meer dan de CLI-opdracht `gem install bundler` met nog een aantal extra controles.
{:.card.card-remark}