---
layout    : course
title     : Custom css
title_long: Bootstrap, hoe custom.css gebruiken
permalink : bootstrap_custom/
published : true
tags      : [boodstrap]
---

## Custom.css

### Aanmaken aangepast stijlblad

Bootstrap heeft een typische look and feel. 
We gebruiken Bootstrap omdat het een goede basis vormt en veel voor opgemaakte elementen bevat waarmee we snel een responsive website kunnen ontwikkelen.
Maar omdat we niet willen dat alle websites op elkaar lijken kunnen we onze eigen stijlblad toevoegen.

Maak een nieuw bestand aan in je CSS-folder en noem het custom.css

> ##### Mappenstructuur Bootstrap :open_file_folder:
> ---
>```
> website
> ├── css/
> │   ├── bootstrap.min.css
> │   └── custom.css
> ├── fonts/
> ├── js/
> └── index.html
>```
{:.card.card-block.files}

In het `<head>`-gedeelte van je website laad je het  nieuwe aangepaste CSS-bestand ***achter*** de standaard stijlbladen van Bootstrap.
{% highlight html linenos %}
{% include_relative _code/bootstrap/custom/head.html %}
{% endhighlight %}{:data-file="index.html"}

### Toevoegen van eigen opmaak

Om opmaak toe te passen aan je webpagina, voeg je gewoon code toe aan je custom.css-bestand.
Stel: we wensen de rondingen van de knoppen in Bootstrap aan te passen. 


{% highlight css linenos %}
{% include_relative _code/bootstrap/custom/borderradius.css %}
{% endhighlight %}{:data-file="css/custom.css"}

Je aangepast stijlblad (custom.css) zal de standaard opmaak van Bootstrap overschrijven. 

![Voor na custom css]({{ site.baseurl }}/images/bootstrap/custom/voorna.png "Voor na custom css")

{% comment %}
<!-- ⚓ Hyperlinks -->
{% endcomment %}
[Het Bootstrap grid-systeem]: http://getbootstrap.com/css/#grid
[Tabel Bootstrap Grid]:       http://getbootstrap.com/css/#grid-options

