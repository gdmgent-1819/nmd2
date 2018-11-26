---
layout    : course
title     : Navbar
title_long: Bootstrap, default navbar
permalink : bootstrap_navbar/
published : true
tags      : [boodstrap]
---

## Navbar
De navbar is een responsive component van het Bootstrap Framework.  
Ze dienen als navigatie voor je website of applicatie. De navigatiebalk wordt bovenaan de pagina geplaatst.   
Afhankelijk van de paginagrootte zal de navigatiebar uitgeklapt of ingeklapt zijn.

Voor je Bootstrap navigatie kan gebruiken heb je de Bootstrap CSS-bestanden en de Bootstrap javascript bestanden nodig.  
Voeg de folder **js** uit je bootstrap-downloadmap toe aan je projectfolder.

> ##### Mappenstructuur Bootstrap :open_file_folder:
> ---
>```
> website
> ├── css/
> │   ├── bootstrap.min.css
> │   └── custom.css
> ├── fonts/
> ├── js/
> │   ├── bootstrap.min.js
> │   └── npm.js
> └── index.html
>```
{:.card.card-block.files}

Implementeer de volgende code in je document om de javascript te laten werken. 

{% highlight html linenos %}
{% include_relative _code/bootstrap/navbar/javascript.html %}
{% endhighlight %}{:data-file="javascript_toevoegen.html"}

Het Bootstrap-javascript bestand werkt met een andere bibliotheek, namelijk **jQuery**. 
Daarom implementeren we eerst de jQuery bibliotheek en vervolgens de Bootstrap-javascript.

Voor de standaard navigatiebalk gebruiken we:  
`<nav class="navbar navbar-default"> ... </nav>`  

In die div maken we vaak twee onderdelen: Ons merk (Logo / websitenaam) en de navigatielijst.  
Ons logo of websitenaam komt in de `.navbar-header` en onze navigatie in de `.navbar-nav`.  
Onze `navbar-header` & `navbar-nav` zit in een div met de klasse `.container-fluid`.   

![Default navbar]({{ site.baseurl }}/images/bootstrap/navbar/navbar.png "Default navbar")

{% highlight html linenos %}
{% include_relative _code/bootstrap/navbar/defaultNavBar.html %}
{% endhighlight %}{:data-file="navbar.html"}

Door `class="active"` aan je lijstelement toe te voegen, duiden we aan op welke pagina we momenteel zitten.

{% highlight html linenos %}
{% include_relative _code/bootstrap/navbar/defaultNavBarActive.html %}
{% endhighlight %}{:data-file="navbar_active.html"}


### Opties

#### Omgedraaide navigatiebalk

De oorspronkelijke navigatiebalk heeft lichte kleuren. Als dit niet bij je website past dan kan je ook gaan voor de omgedraaide navigatiebalk.

In onze `nav-tag` vervangen we de klasse `navbar-default` door `navbar-inverse`.

![Inverse navbar]({{ site.baseurl }}/images/bootstrap/navbar/navbarinverse.png "Inverse navbar")

{% highlight html linenos %}
{% include_relative _code/bootstrap/navbar/defaultInverseNavBar.html %}
{% endhighlight %}{:data-file="navbar_inverse.html"}


#### Fixed navigatiebalk

Standaard verdwijnt de navigatiebalk bij het scrollen  maar de navigatiebalk kan ook bovenaan of onderaan gefixed staan.  
Bij een fixed navigatiebalk zal de balk altijd zichtbaar zijn onafhankelijk van het scrollen. 

In onze `nav-tag` voegen we de klasse `navbar-fixed-top` of `navbar-fixed-bottom` toe.

{% highlight html linenos %}
{% include_relative _code/bootstrap/navbar/navbarFixed.html %}
{% endhighlight %}{:data-file="navbar_fixed.html"}

#### Rechts uitgelijnde navigatiebalk

Met de klasse `navbar-right` in onze navigatie-lijst kunnen we knoppen rechts uitlijnen.

![rechts navbar]({{ site.baseurl }}/images/bootstrap/navbar/navbarright.png "rechts navbar")

{% highlight html linenos %}
{% include_relative _code/bootstrap/navbar/rightNavBar.html %}
{% endhighlight %}{:data-file="navbar_right.html"}



### Collapsing the navigation bar

De navigatiebalk neemt te veel ruimte in op een klein scherm.  
We kunnen de navigatiebalk onzichtbaar maken en enkel tevoorschijn laten komen indien nodig.  
Dit doen we door een button toe te voegen aan onze de `nav-header` en vervolgens een div met klasse `collapse navbar-collapse` rond onze navigatielijst toe te voegen.
Let op dat je in de `target-tag` van je button de zelfde waarde schrijft als de ID die je gebruikt in de nieuwe div die rond de navigatielijst.

In het voorbeeld gebruiken we `myNavbar` als ID.

{% highlight html linenos %}
{% include_relative _code/bootstrap/navbar/collapseNavBar.html %}
{% endhighlight %}{:data-file="collapse_navbar.html"}

### Verticale navigatiebalk

Een veticale navigatiebalk kan ook van toepassing zijn. Hieronder kan je voorbeeldcode vinden die zich basseert op bootstrap.   
[Verticale navigatiebalk](http://codepen.io/bartmi/pen/yavKNa)