---
layout: course
title: Grid
title_long: Het Bootstrap grid-systeem
permalink: bootstrap_grid/
published: true
tags:
  - bootstrap
---

## Het Bootstrap Grid-systeem

Het grid-systeem gebruikt door Bootstrap vertoont heel wat gelijkenissen met het grid-systeem dat we in WebDesign II gebruikten. Op de website van Bootstrap vind je alle uitleg die je nodig hebt.

[Het Bootstrap grid-systeem]

### Mobile first & Media Queries

Bootstrap houdt zich sterk aan de regel "Mobile First". Dit betekent dat het grid-systeem standaard is afgestemd op de kleinste toestellen (smart phones). De aanpassingen voor grotere schermen worden dan geschreven binnen de declaraties van de media queries. De mobile first-regel dwingt ons in de media queries vanuit het kleinste scherm te denken. Zo kent bootstrap de volgende 4 media queries.

- extra kleine schermen (extra small devices) smart phones: < 768px
- kleine schermen (small devices) tablets: ≥ 768px
- gewone computerschermen (medium devices) portables: ≥992px
- grote computerschermen (large devices) desktops: ≥1200px

[Tabel Bootstrap Grid]

Wat opvalt in het lijstje is dat de schermbreedte van de eerste als "<" (tot 768px) wordt genoteerd. Bij elke volgende querie wordt er "≥" (vanaf zoveel pixels) gebruikt. Hierachter schuilt de Mobile first-regel. Eigenlijk wordt er geen media querie gebruikt voor kleine schermen. Alle css hiervoor vindt je in het "standaard-deel" van je css-bestand. Sterker nog zolang je niet ingrijpt (via een media querie) blijft deze css gelden voor je ganse website.

> ##### **Tip** :bulb:
> ---
> Het is dus handig onmiddellijk de media queries zoals bootstrap die voorziet ook op te nemen in je eigen custom.css. Meer daarover in het het hoofdstuk over de custom css.
{:.alert.alert-info}

### Normalize.css

Is reeds in de bootstrap.css opgenomen, we hoeven deze dus niet appart op te roepen in de head van onze pagina.

### Kolommen

Ook nu werken we met een grid gebasseerd op 12 kolommen. En net zoals het grid gebruikt in WebDesign II worden de expansie over de kolommen heen en de hieraan gekoppelde breedte voorgedefiniëerd ditmaal in de bootstrap.css of bootstrap.min.css

De breedte van de kolommen wordt in % uitgedrukt: vb 12 = 100%

De classesbenaming voor de verschillende schermbreedtes zijn

- extra kleine schermen (extra small devices) smart phones: ***.col-xs-#***
- kleine schermen (small devices) tablets: ***.col-sm-#***
- gewone computerschermen (medium devices) portables: ***.col-md-#***
- grote computerschermen (large devices) desktops: ***.col-lg-#***

Het*** # ***staat uiteraard voor het aantal kolommen die je div overspant.

#### Floating

Naast de breedte is een van de belangrijkste standaard eigenschappen van een kolom dat deze de eigenschap ***float:left*** meekrijgt. Hierdoor komen de kolommen naast elkaar te staan.

#### Ruimte tussen de kolommen

Bootstrap gebruikt ***padding*** (en geen margins) om de inhoud tussen de kolommen visueel te scheiden. Elke kolom ongeacht de schermbreedte (media query) heeft zowel links als rechts 15px padding. Wat de totale ruimte tussen twee inhouden op 30px brengt.

### Row

Ook in bootstrap wordt een verzameling kolommen ***verplicht omgeven door een row*** (div met class="row").
De belangrijkste eigenschap van een row is het stoppen van de float van de kolommen.

{% highlight css linenos %}
{% include_relative _code/row.css %}
{% endhighlight %}{:data-file=".css"}

Een row krijgt een ***flexibele breedte*** mee via de css property ***display:table***

> ##### **Opmerking** :point_up:
> ---
> Een row krijgt zowel links als recht een negatieve marge van -15px. Dit zorgt ervoor dat de eerste en de laatste kolom netjes tegen de rand van de container aansluit.
{:.alert.alert-info}

vb: probeer even zelf uit wat er gebeurt als je de negatieve marge op de row wegneemt
<iframe height='237' scrolling='no' src='//codepen.io/bartmi/embed/NRwxjE/?height=237&theme-id=dark&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/bartmi/pen/NRwxjE/'>Bootstrap grid 1:  row en cols</a> by Bart Missant (<a href='http://codepen.io/bartmi'>@bartmi</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

### Container

Boven dit alles staat een container. Een container is de parent van één of meerdere rows.

Bootstrap onderscheidt twee container classes:

- ***container***: heeft een ***vaste breedte*** afhankelijk van de media querie waarin ze voorkomt:- extra kleine schermen (extra small devices) smart phones: ***geen breedte***
  - kleine schermen (small devices) tablets: ***750px***
  - gewone computerschermen (medium devices) portables: ***970px***
  - grote computerschermen (large devices) desktops: ***1170px***
- ***container-fluid***: wanneer je een ***flexibele schermbrede layout*** wenst

#### Ruimte naast de container

Zowel .container als .container-fluid krijgen links en rechts een ***padding*** van 15px mee.
Een .container is altijd in het midden van het scherm gepositioneerd.

## Samengevat

> ##### **Opmerking** :point_up:
> kolommen (.col-) zitten altijd in een rij (.row) deze hebben altijd in een container (.container of .container-fluid)
> 
{:.alert.alert-info}

## uitbreidingen

## Combinatie container-fluid + container

band tot tegen zijkanten scherm, inhoud vast in het mi

### kolommen in kolommen

Plaats je in een kolom nieuwe kolommen dan plaats je ook deze in een nieuwe row binnen de parent-kolom.

{% highlight html linenos %}
{% include_relative _code/bootstrap/grid/col_inside_col.html %}
{% endhighlight %}{:data-file=".html"}

<div class="container">
<div class="row">
    <div class="col-md-8">
        <div class="row">
            <div class="col-md-6">
             col-6 want 50%
            </div>
            <div class="col-md-6">
                col-6 want 50%
            </div>
        </div>
        <div class="col-md-4">
            col-4 want zusje van col-8
    </div>
    </div>
</div>
</div>

{% comment %}
<!-- ⚓ Hyperlinks -->
{% endcomment %}
