---
layout   : course
permalink: workflow/design/sitemap/
published: true
#
abbreviations:
  - computer
  - education
hyperlinks:
  - software
title: Sitemap
---
{%- include includes.md %}

Wat is een sitemap?
-------------------

> Definitie
> ---
> Een **sitemap** *(Eng.: site map)* is een werkdocument dat een visuele voorstelling van de structuur van een website bevat. Het toont hoe verschillende pagina's met elkaar verbonden zijn.
{:.card.card-definition}

Typische structuren voor websites:

Hiërarchische structuur
: Een boomstructuur die vertrekt vanaf de homepagina.

Webstructuur
: Alle pagina's zijn met alle andere pagina's verbonden.

Lineaire structuur
: De ene pagina volgt op de andere pagina.

SPA
: Een *Single-Page Application* noemt men soms ook een *one-pager*.
: Een pagina bevat de inhoud van meerdere pagina's. De inhoud wordt toegevoegd zonder dat de pagina opnieuw ingeladen moet worden.

In de praktijk zijn de meeste websites een combinatie van deze vier types.

> Opgelet
> ---
> Binnen de context van een website wordt de term **sitemap** ook gebruikt voor een lijst met koppelingen naar alle pagina's op een website. Het doel van deze lijst is de bezoeker of zoekmachine een overzicht te geven van alle pagina's.
{:.card.card-warning}

Hoe maak je een sitemap?
------------------------

Iedere pagina krijgt een apart blokje en verbindingslijnen (**zonder pijlen**) met bovenliggende en onderliggende items. Alle pagina’s krijgen een titel en een paginanummer dat later gebruikt kan worden tijdens verdere ontwikkeling.

 - Pagina blokje voorgesteld door een volle lijn
   Dit is een nieuwe pagina
 - Pagina blokje voorgesteld door een streepjeslijn
   Een andere inhoud die geladen wordt binnen eenzelfde pagina
 - Stapel blokjes *(Eng.: stack)*
   Een type pagina die meerdere malen gebruikt wordt met verschillende inhoud

Een website heeft meestal een beginpagina, de **homepagina**. Vanuit deze pagina kan naar de onderliggende pagina's gelinkt worden.

Elke pagina stel je voor door een blokje en geef je een naam en een referentienummer, zodat wireframes en screendesigns hiernaar kunnen verwijzen.

 - de beginpagina krijgt altijd het nummer `0.0`;
 - de eerst volgende pagina is dan `1.0`;
 - een onderliggende pagina krijgt dan het nummer `1.1`.

Wanneer een bepaald type pagina meerdere keren terugkeert in de structuur (bv. detailpagina's van producten) dan stellen we dit visueel voor met een stapel van blokjes en krijgt als laatste deel in het referentienummer een `x` (Bv. `1.x`)

![Voorbeeld sitemap](http://www.arteveldehogeschool.be/campusGDM/wanm/mod_wanm/workflow/sitemap1.jpg)

Waarvoor gebruik je een sitemap?
--------------------------------

Een website is een verzameling van webpagina's. Een sitemap geeft een overzicht van waar die pagina's zich bevinden en hoe ze zich tot elkaar verhouden.

Wie is er bij betrokken?
------------------------

Maken sitemaps:

 - Informatiearchitect
 - Interactieontwerper

Baseren zich op:

 - Interactieontwerper
 - Ontwerper (visual designer, UI designer)
 - Ontwikkelaar (developer, programmeur, softwarearchitect)
 - Copywriter

> Bronnen
> ---
> - Brown, D.M. (2007). *Communicating Design.* New Riders.
> - Garrett, J.J. (2003). *The Elements of User Experience.* New Riders.
{:.card.card-source}


Voorbeeld
---------
In onderstaand voorbeeld zie je de sitemap van een fietsenwinkel met een online shop.

{% include shared/covers.html covers=site.data.voorbeelden.sitemap.external %}

Software
--------

 - [Adobe Illustrator CC][]
 - [XMind Free][] (exporteer naar SVG om in een ander programma te importeren)
 - …