---
layout   : course
permalink: generators/jekyll/opmaak/
published: false
#
abbreviations:
  - computer
  - education
hyperlinks:
  - csse
  - technology
title     : Opmaak
title_long: Opmaak met Sass
---
{%- include includes.md %}

Opmaak in Jekyll kan via de gewone CSS, maar Jekyll ondersteunt ook Sass.

Sass
----

> Zie ook
> ---
> - [SCSS][]
{:.card.card-link}

> Definitie
> ---
> **[Sass][]** is een **CSS-preprocessor** die Sass- of SCSS-code omzet naar gewone CSS.
{:.card.card-definition}

### Wat is Sass en SCCS?

De Sass CSS-preprocessor ondersteunt 2 syntaxissen:

 - Sass (`*.sass`)  
   De originele Sass-syntaxis. Is compacter dan CSS, maar CSS-syntaxis is er niet compatibel mee.
 - SCSS (`*.scss`)  
   De nieuwere Sass-syntaxis. Is een uitbreiding van CSS, waardoor standaard CSS er compatibel mee is.

> Opmerking
> ---
> CSS is ook geldige SCSS, maar is geen geldige Sass. Vandaar dat SCSS de voorkeur krijgt.
>
> Je kan SCSS een beetje beschouwen als een toekomstige versie van CSS die je nu al kan gebruiken.
{:.card.card-remark}

### Waarom SCSS gebruiken?

 - Het bespaart werkt (op lange termijn)!
 - Het maakt het structureren van code makkelijker en overzichtelijker.
 - Het voegt nieuwe functionaliteiten toe die (nog) niet in CSS bestaan:
   - **Nesten** van stijlen, net zoals je HTML nest;
   - **Scripting** om bijvoorbeeld herhalingen te vermijden en berekeningen uit te voeren binnen een bepaalde context:
     - Data types;
     - Variabelen;
     - Functies;
   - …

Bootstrap
---------

Sinds versie 4 maakt [Bootstrap][] standaard gebruik van [SCSS][], in Bootstrap 3 was dit nog standaard [Less][], maar er was ook al een SCSS-variant.

### Git Submodule

De broncode van Bootstrap is dus geschreven in SCSS, daarom kunnen we die rechtstreeks gaan gebruiken en aanpassen. 

We kunnen de broncode van Bootstrap toevoegen aan ons eigen project via een Git Submodule. Dit zal de Git-repository van Bootstrap koppelen aan onze eigen Git-repository. In onze eigen repository zal de code van Bootstrap niet gekopieerd worden, maar enkel gekoppeld. Dat scheelt qua opslagruimte en is bovendien heel makkelijk te updaten met een `git pull`.

#### Submodule toevoegen

{% highlight posh %}
PS> c 1718-nmd2-code-jekyll
PS> git submodule add --branch v4-dev --depth 1 https://github.com/twbs/bootstrap/ _vendor/bootstrap
{% endhighlight %}

> Opmerking
> ---
> Er wordt enkel een verwijzing naar de submodule bewaard in je repository, niet de submodule zelf.
{:.card.card-remark}

#### Submodule opnieuw downloaden

Als je je repository kloont, zal je de submodule opnieuw moeten downloaden, want die is niet bewaard in je eigen repository.

Er moeten 3 stappen doorlopen worden:

 1. de submodule initialiseren;
 1. de submodule updaten;
 1. de submodule op branch `v4-dev` zetten.

{% highlight posh %}
PS> c 1718-nmd2-code-jekyll
PS> git submodule update --init
PS> git submodule foreach 'git checkout v4-dev'
{% endhighlight %}