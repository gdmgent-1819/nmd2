---
layout   : course
permalink: workflow/design/wireframes/
published: true
#
abbreviations:
  - education
hyperlinks:
  - csse
  - education
  - software
title: Wireframes
---
{%- include includes.md %}

Wat is een wireframe?
---------------------

> Definitie
> ---
> Een **wireframe** is een draadmodelweergave van (een toestand van) een **view** van een website (of mobile app, wearable, ...) dat toont waar de **inhoud**, **basisstructuur** en **functionaliteiten** komen. 
{:.card.card-definition}

Wie maakt wireframes?
---------------------

De personen die [wireframes][] maken hebben de rol van informatiearchitect en/of interactieontwerper.

Waarom worden wireframes gemaakt?
---------------------------------

Een wireframes is een **communicatiemiddel** waarmee de informatiearchitect en/of de interactieontwerper communiceert met de klant, maar ook naar de grafisch ontwerper en de softwareontwikkelaars.

Wireframes moeten dus voldoende, en eenduidige informatie bevatten, want op basis van &mdash; onder meer &mdash; de wireframes zal de grafisch ontwerper een [visual design][Visual Designs] maken en de softwareontwikkelaar een applicatie te bouwen.

Wireframes worden aan het begin van het proces gemaakt, want een wijziging aanbrengen in een wireframe is minder arbeidsintensief dan in een visueel ontwerp en veel minder dan in een reeds gebouwde applicatie. Het is normaal dat er in latere fases van het proces dingen wijzigen, maar dan is het meestal weinig zinvol om de wireframes nog te wijzigen.

> Opmerking
> ---
> Wireframes worden gemaakt om tijd te besparen op lange termijn en fouten te vermijden. Wireframes worden dus **nooit** na het visual design gemaakt!
{:.card.card-remark}

Hoe maak je een wireframe?
--------------------------

Voor elke view (pagina) op de [sitemap][] wordt een of meerdere wireframes opgesteld die de view zowel inhoudelijk als functioneel omschrijven. Kort gezegd: wat komt waar? 

> Opmerking
> ---
> Voor **responsive** ontwerpen kunnen meerdere wireframes per view nodig zijn.
{:.card.card-remark}

### Dynamische pagina's

Pagina's die stuctureel hetzelfde zijn, maar waarvan de inhoud dynamisch verandert, worden allemaal door eenzelfde wireframe voorgesteld. De begeleidende tekst moet dit wel vermelden. Bijvoorbeeld productpagina's op een cataloguswebsite.

Op de sitemap worden dit soort pagina's door een **stapel** *(Eng.: stack)* voorgesteld.

### Toestanden *(Eng.: states)*

Een pagina die door gebruikersinteractie structureel of visueel kan wijzigen moet door verschillende wireframes voorgesteld worden. Bijvoorbeeld een formulierpagina met verschillende toestanden: begintoestand, fouttoestand (ingevulde formulieren), successtoestand (formulier succesvol verstuurd), …

### Wat zet je op een wireframe

 - Rand van de pagina.
 - Paginatitel
 - Referentienummer (en indien van toepassing ook de variant)
 - Begeleidende tekst buiten de pagina.
 - Elementen op de pagina:
   - navigatie;
   - tekst;
   - inhoudelijke afbeeldingen;
   - formulieren
   - specifieke zones
   - …

### Placeholders

Als de inhoud nog ontbreekt, dan gebruik je **placeholders**. Een placholder voor een inhoudelijke afbeelding stel je voor door een rechthoek met een kruis erdoor. Decoratieve afbeeldingen worden niet voorgesteld op een [wireframe][Wireframes], omdat dit tot het [visueel ontwerp][Visual Designs] behoort. Ook masking of masking (bijvoorbeeld een ronde foto) is eerder voor het visueel ontwerp dan de wireframe.

Elementen die tot het visueel ontwerp behoren &ndash; zoals typografie, kleur en decoratieve afbeeldingen &ndash; worden liefst achterwege gelaten. Dit leidt af van het eigenlijk doel van dit werkdocument.

Inhoudelijke elementen zoals tekst en illustraties gebruik je liefst wel, want dat heeft invloed op de informatiearchitectuur.

> Tip
> ---
> Tekst die nog niet definitief is zet je tussen accolades: `{`…`}`.
{:.card.card-tip}

Voorbeelden
-----------

### Mobile (studenten)

{% include shared/covers.html covers=site.data.voorbeelden.wireframes.internal.mobile %}

{% comment %}
### Desktop (studenten)

{% include shared/covers.html covers=site.data.voorbeelden.wireframes.internal.desktop %}
{% endcomment %}

Software
--------

 - [Adobe Illustrator CC][]
 - [Adobe XD CC][]
 - …

> Bronnen
> ---
> - Brown, D.M. (2007). *Communicating Design.* New Riders.
> - Garrett, J.J. (2003). *The Elements of User Experience.* New Riders.
> - Treder, M. (2016, September 8). [Wireframing, Prototyping, Mockuping – What’s the Difference?](https://designmodo.com/wireframing-prototyping-mockuping/) *Designmodo.*
{:.card.card-source}
