---
layout   : course
permalink: jekyll/
published: true
#
abbreviations:
  - computer
hyperlinks:
  - csse
  - software
title: Jekyll
---
{%- include includes.md %}

> Zie ook
> ---
> - [Jekyll][]
> - [Creating Blogs with Jekyll](https://link.springer.com/book/10.1007/978-1-4842-1464-0) (Dhillon, 2016)  
>   Gratis te downloaden als je via het schoolnetwerk werkt.
> - [GitHub Pages](https://pages.github.com)
{%- comment %}
> - [GitLab Pages](https://pages.gitlab.io)
{%- endcomment %}
{:.card.card-book}

Jekyll is de [populairste opensource SSG](https://www.staticgen.com/jekyll) op dit ogenblik.

> Definitie
> ---
> Een **Static Site Generator (SSG)** is een programma waarmee een **statische website** gegenereerd wordt op basis van inhoud en sjablonen.
{:.card.card-definition}

Een SSG kan gebruik maken van een database, maar de gegenereerde website kan op elke HTTP-server geplaatst worden en heeft zelf geen database meer nodig.

> Zie ook
> ---
> - [Why Static Website Generators Are The Next Big Thing](https://www.smashingmagazine.com/2015/11/modern-static-website-generators-next-big-thing/) (Smashing Magazine, 2015-11)
> - [StaticGen - Top Open-Source Static Site Generators](https://www.staticgen.com)
{:.card.card-link}

Jekyll maakt gebruik van een aantal technologieën, waaronder [Ruby][], [Liquid][], [Markdown][] en [Sass][].

| Onderdeel         | Taal         | Omgezet naar | Optioneel                           |
|-------------------|--------------|--------------|-------------------------------------|
| Programmering     | [Ruby][]     |              | Ja, enkel als je eigen plugins wil. |
| Sjablonen         | [Liquid][]   |              |                                     |
| Inhoud            | [Markdown][] | HTML         | Ja, mag ook direct HTML zijn.       |
| Opmaak            | [Sass][]     | CSS          | Ja, mag ook direct CSS zijn.        |
{:.table.table--primary}