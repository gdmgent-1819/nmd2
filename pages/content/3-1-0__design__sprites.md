---
layout    : course
title     : Sprites
title_long: CSS Sprites
permalink : design/sprites/
published : true
tags      : [Sprites]
---



Een **image sprite** is een groot document dat alle afbeeldingen van een webpagina samenbrengt.  
Het is een vaak gigantische png of jpg. Dit is bijvoorbeeld de sprite die yahoo.com momenteel gebruikt op hun homepagina (klik om een grotere versie te zien):

![Yahoo sprite]({{ site.baseurl }}/images/design/yahoo-sprite.png "Yahoo sprite")

Yahoo plaatst er alle afbeeldingen op die tot de interface van de website behoren: menu-icoontjes, weer-icoontjes, logo’s, user interface beeldjes…

Ook Facebook maakt er gebruik van:

![Facebook sprite]({{ site.baseurl }}/images/design/facebook-sprite.png "Facebook sprite")

## Waarom in godsnaam?

Het idee achter een sprite is simpel: als een gebruiker naar je webpagina surft, moet er maar 1 afbeeldingsbestand gedownload worden.  
Meteen kunnen dan alle beeldjes getoond worden die tot de interface behoren.  
Dat gaat een pak sneller dan 40 of 50 aparte kleine beeldjes laden.  
Je vervangt 50 kleine http-requests door 1 (weliswaar grote) request. Minder requests levert altijd een winsituatie op.

Daarenboven is de samengestelde bestandsgrootte van vele kleine beeldjes bijna altijd groter dan wanneer je ze combineert tot 1 beeld.  
Er moeten dus ook minder bytes gedownload worden. En ook dat levert dus snelheidswinst op.

## Overtuigd! Hoe toon je het juiste beeldje?

Met CSS! Je laadt de volledige sprite bijvoorbeeld in als achtergrondafbeelding, geeft je element een breedte en hoogte, en gebruikt `background-position` om de positie van het achtergrondbeeld te bepalen:

{% highlight css linenos %}
{% include_relative _code/design/sprite_01.css %}
{% endhighlight %}{:data-file="style.html"}

Wat verder maak ik gebruik van deze minisprite:

![Mini sprite]({{ site.baseurl }}/images/design/mini-sprite.png "Mini sprite")

Bekijk even de HTML en CSS in het voorbeeld hieronder. Omdat de div geen content heeft, krijgt die ook geen hoogte. Block-level elementen nemen standaard de volledige beschikbare breedte in.  
Ik geef de div daarom een hoogte van 150px. De `background-image` wordt automatisch herhaald over de x-as en de y-as, vandaar de herhaling van onze sprite.

<iframe width="100%" height="400" src="//jsfiddle.net/rutsaert/oetpesv7/4/embedded/result,html,css" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
Ik wil het konijntje laten zien, en via Photoshop weet ik dat het konijn 17 pixels breed is en 20 pixels hoog. Ik maak mijn div dus exact zo:

<iframe width="100%" height="400" src="//jsfiddle.net/rutsaert/oetpesv7/5/embedded/css,html,result" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
Omdat de linker bovenhoek van de achtergrondafbeelding in de linker bovenhoek van de div gepositioneerd wordt, krijgen we de linker bovenhoek van de achtergrondafbeelding te zien: het stukje van 17 x 20 pixels waarin een deel van de vogel te zien is.

Ik moet de <code>background-position</code> dus aanpassen. Die CSS property heeft 2 waarden nodig: de eerste waarde is de verschuiving van mijn achtergrondbeeld op de x-as en de tweede waarde is de verschuiving van het beeld op de y-as. 

Even rekenen: ik moet het beeld 33 pixels naar links verschuiven, want het konijn staat 33 pixels van de linkerkant in mijn sprite. Ik moet het beeld niet verschuiven op de y-as want het konijn staat helemaal tegen de bovenkant van mijn sprite. Dat geeft volgende CSS:

<iframe width="100%" height="400" src="//jsfiddle.net/rutsaert/oetpesv7/6/embedded/result,css,html" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
En zowaar: zoals je kan zien komt het konijntje te voorschijn! Ik kan nu nog verder gaan, en bijvoorbeeld ook het roze konijntje als achtergrondafbeelding voor de hoverstatus instellen.  
Het roze konijntje bevindt zich op dezelfde x-positie op de sprite, maar op een andere y-positie:

<iframe width="100%" height="400" src="//jsfiddle.net/rutsaert/oetpesv7/8/embedded/css,result,html" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
Zoals je kan zien verschijnt het roze konijntje wanneer je over de div beweegt met de muisaanwijzer.</p>

## Nog een voorbeeld

In deze jsfiddle gebruik ik <a href="images/yahoo-sprite.png" class="">de Yahoo sprite</a>. Ik gebruik ook CSS generated content (via <code>::before</code> in dit geval) om de icoontjes in de navigatie te plaatsen. Check de code maar eens:

<iframe width="100%" height="400" src="//jsfiddle.net/rutsaert/7Lmtnb65/1/embedded/result,html,css" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

## Veel werk!

Sprites samenstellen vergt veel werk: per beeldje dat je in de interface van je website gebruikt, moet je de sprite aanpassen. Tegelijk moet je op zoek gaan naar de juiste x -en y-positie van je iconen en logo’s.  
Maar het vergt de moeite: pagina’s die snel laden worden door de gebruiker als veel aangenamer ervaren. 

En er zijn ook heel wat tools die je kunnen helpen om sprites te maken: Google maar eens…

