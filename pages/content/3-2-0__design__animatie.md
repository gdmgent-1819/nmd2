---
layout    : course
title     : Animaties en Transities
title_long: CSS animaties en transities
permalink : design/animatie-transities/
published : true
tags      : [Animation, Transitions]
---



Animatie is een middel om een verhaal te vertellen, de aandacht van je gebruiker te trekken (animaties staan hoog in de visuele hiërarchie) en een middel om de gebruikerservaring van je site te vergroten. Animaties maken vaak een essentieel deel uit van de werking van de gebruikersinterface. 
Animatie verkrijgen we door gebruik te maken van **CCS Animations** of **CSS Transitions** 

<!-- ![Facebook sprite]({{ site.baseurl }}/images/design/facebook-sprite.png "Facebook sprite") -->

## CSS Animations

Bij het werken met CSS Animations defineer je eerst de animatie via de @keyframes stijlregel. Binnen de @keyframes stijlregel specifieer je op welke percentages veranderingen in stijlregels wil zien. 0% en 100% kunnen ook vervangen worden door de woorden 'from' en 'to'. 
Vervolgens koppel je deze animatie aan een klasse via de stijlregel 'animation-name'. 

{% highlight css linenos %}
{% include_relative _code/design/keyframes.css %}
{% endhighlight %}{:data-file="style.html"}

<a href="http://codepen.io/stanseel/pen/rWYyLm" target="blank">**Animation Codepen voorbeeld uit de les**</a> 

 <a href="http://www.w3schools.com/css/css3_animations.asp" target="blank">Meer over CSS animaties op W3Schools</a>

## CSS Transities

CSS transities bieden je de mogelijkheid om een element van één staat (uitzicht, positie, ...) naar een nieuwe staat te laten evolueren over een bepaalde tijd. Er is geen mogelijkheid om meerdere keyframes te definiëren zoals bij CSS animations. 
Transities zijn daarom wel eenvoudiger toe te passen. 

{% highlight css linenos %}
{% include_relative _code/design/transities.css %}
{% endhighlight %}{:data-file="style.html"}

In bovenstaand voorbeeld zal elke verandering in de waarde van 'margin-left' (bijvoobeeld in de bepaling van de :hover status) uitgevoerd worden als een animatie over 0.5 seconden. 

<a href="http://codepen.io/stanseel/pen/BLbNmq" target="blank">**Transition Codepen voorbeeld uit de les**</a> 

 <a href="http://www.w3schools.com/css/css3_transitions.asp" target="blank">Meer over CSS transities op W3Schools</a>


