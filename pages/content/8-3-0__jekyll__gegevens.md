---
layout   : course
permalink: generators/jekyll/gegevens/
published: false
#
abbreviations:
  - computer
  - education
hyperlinks:
  - csse
locals:
  - jekyll
title: Gegevens
---
{%- include includes.md %}

In Jekyll worden gegevens opgeslagen in het [YAML][]-formaat.

Wat is YAML?
------------

> Zie ook
> ---
> - [YAML][]
> - [YAML 1.2 Specificaties](http://www.yaml.org/spec/1.2/spec.html)
{:.card.card-link}

> Definitie
> ---
> - YAML is een standaard voor gegevensserialisatie[^serialisatie], die geschikt is voor alle programmeertalen en makkelijk leesbaar is voor mensen.
{:.card.card-definition}

[^serialisatie]: Serialisatie is een term uit de computerwetenschappen die wil zeggen dat gegevens geschikt gemaakt worden om op te slaan.

YAML is dus een formaat waarin gegevens opgeslagen kunnen worden, en in vergelijking met andere gegevensformaten *(Eng.: data formats)* is het makkelijk te lezen en te gebruiken door mensen.

YAML toepassen in Jekyll
------------------------

YAML wordt in Jekyll op drie plaatsen gebruikt:

 - In het bestand `_config.yml`.
 - Specifieke YAML-bestanden.
 - In de Jekyll **Front Matter** van een bestand.

### Jekyll Front Matter

Helemaal bovenaan elk bestand dat door Jekyll verwerkt moet worden moet Front Matter geplaatst worden. Front Matter bestaat uit twee regels met telkens `---` (drie koppeltekens), waartussen optioneel YAML geschreven kan worden.

{% highlight html linenos %}
---
---
<?DOCTYPE html>
<meta charset="utf-8">
<title>Hallo, Wereld!</title>
{% endhighlight %}{:data-file="index.html"}

Hoe werkt YAML?
---------------

> Opgelet
> ---
> Bij YAML moet je heel nauwgezet **insprongen** toepassen (twee spaties per keer), want de betekenis van de code verandert met elke insprong.
{:.card.card-warning}

> Tip
> ---
> Gebruik [YAML Lint](http://www.yamllint.com) om de YAML-code te controleren (en op te schonen).
{:.card.card-tip}

### Commentaar

{% highlight yml %}
# Dit is commentaar in YAML
{% endhighlight %}

### Scalaire gegevens

Scalaire gegevens zijn de meest eenvoudige gegevens:

 - **Boolean** *(Ned.: booleaanse waarde)*
 - **Integer** *(Ned.: geheel getal)*
 - **Float** *(Ned.: zwevendekommagetal)*
 - **String** *(Ned.: tekenstring)*
 - **Date** *(Ned.: datum)*

{% highlight yml %}
booleaanse-waarde: true
geheel-getal: 1
zwevendekommagetal: 1.2
tekst: Lorem ipsum.
tekst-tussen-enkele-aanhalingstekens: 'Lorem ipsum.'
tekst-tussen-dubbele-aanhalingstekens: "Lorem ipsum."
tekst-over-meerdere-regels: |
  Lorem ipsum dolor sit amet consectetur adipisicing elit.
  Sint beatae esse facilis possimus in hic, odio cumque, mollitia id praesentium, corrupti voluptas laborum nemo?
  Necessitatibus blanditiis sed itaque error modi.
datum: 2017-09-21
{% endhighlight %}

> Opgelet
> ---
> Meestal zijn **apostroffen** (`'`) of **aanhalingstekens** (`"`) voor tekst niet nodig.
>
> Maar wel **verplicht** als er tekens in de tekst staan die een bepaalde betekenis hebben in YAML, zoals bijvoorbeeld een **dubbelepunt** (`:`).
{:.card.card-warning}

{% highlight yml %}
tekst: 'John Doe zegt: "Hallo!"'
{% endhighlight %}

### Hash (Object)

{% highlight yml %}
persoon:
  voornaam: Jane
  familienaam: Doe
{% endhighlight %}

In bovenstaand voorbeeld zijn `voornaam` en `familienaam` eigenschappen van `persoon`.

> Opgelet
> ---
> Eigenschappen van een Hash moeten een unieke naam hebben!
{:.card.card-warning}

### Sequence (Array)

{% highlight yml %}
voornamen:
  - Jane
  - John
{% endhighlight %}

> Opmerking
> ---
> De lijstitems mogen wel meerdere keren exact dezelfde waarde hebben.
{:.card.card-remark}

### Combinatie

{% highlight yml %}
persoon:
  voornamen:
    - Jane
    - John
  familienaam: Doe
{% endhighlight %}

{% highlight yml %}
personen:
  -
    voornamen:
      - Jane
      - John
    familienaam: Doe
  -
    voornamen:
      - Jack
    familienaam: Doe
{% endhighlight %}

### Geavanceerde YAML

Bovenstaande voorbeelden tonen de meestgebruikte functionaliteiten van YAML, maar YAML kan nog veel meer.

> Zie ook
> ---
> - [YAML Cheat Sheet](http://lzone.de/cheat-sheet/YAML)
> - [YAML 1.2 Specificaties](http://www.yaml.org/spec/1.2/spec.html)
{:.card.card-link}