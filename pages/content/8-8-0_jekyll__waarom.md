---
layout   : course
permalink: jekyll/jekyll
published: true
#
title: Waarom Jekyll
---

## Een statische website

![figuur 1]({{ site.baseurl }}/images/jekyll/jekyll_werking_1.png "figuur 1")

Bij het maken van een statische website, creeëren we telkens opnieuw een html-bestand waarin we telkens opnieuw elk component moeten verwerken. Best fijn als we slechts5 pagina's hebben, maar quasi onwerkbaar als de website meer dan tien pagina's wordt.

## Terugkerende elementen

![figuur 2]({{ site.baseurl }}/images/jekyll/jekyll_werking_2.png "figuur 2")

## Static Site Generator

Bij een static site generator zoals Jekyll, hebben we de mogelijkheid om lay-out en content van elkaar te scheiden. Dit zelfde idee vinden we terug bij de bekende CMS zoals WordPress, Joomla, Drupal, … Waar de template los staat van de inhoud.
Bij Jekyll huizen we deze templates in de map "_layouts".

![figuur 3]({{ site.baseurl }}/images/jekyll/jekyll_werking_3.png "figuur 3")

## Meerdere type lay-outs

Het is altijd leuk wat afwisseling in de lay-outs te bekomen. Zo kom je als nsel tot de behoefte om een meerdere lay-outs te ontwerpen. Vergelijk dit met de basispagain's in inDesign.

![figuur 4]({{ site.baseurl }}/images/jekyll/jekyll_werking_4.png "figuur 4")

## Terugkerende componenten

Deze verschillende type lay-outs hebben uiteraard ook componenten die op elke pagina terugkeren. Denk aan de navigatie en de footer. De html-code voor elk  afzonderlijk component kan je apart aanmaken in de map "_includes". Wijzig je dan iets in de foot dan wijzigt dit in elke lay_out en uiteraard ook op elke pagina.
"includes" kan je uiteraard ook in de inhoud van een enkele pagina oproepen.

![figuur 5]({{ site.baseurl }}/images/jekyll/jekyll_werking_5.png "figuur 5")
