---
layout   : course
permalink: git-en-github/
published: true
#
abbreviations:
  - cli
  - computer
  - education
hyperlinks:
  - software
title: Git & GitHub
---
{%- include includes.md %}

GitHub Classroom
----------------

Klik op de *GitHub Classroom*-koppeling die je gekregen hebt, zodat er een nieuwe repository aangemaakt wordt voor jou. Deze repository ga je dan eerst klonen.


Repository Klonen
-----------------

Ga naar de `Code`-map

{% highlight posh %}
PS> c
{% endhighlight %}

Maak de map `1819-nmd2-code` voor dit OLOD.

{% highlight posh %}
PS> mkdir 1819-nmd2-code
PS> c 1819-nmd2-code
{% endhighlight %}

Kloon de nieuwe repository (vervang "«repositorynaam»" door de echte naam van je repository).

{% highlight posh %}
PS> git clone https://github.com/gdmgent-1819-nmd2/«repositorynaam».git
{% endhighlight %}

Wijzigingen Opslaan
-------------------

> Workflow:
>
> 1. Bestanden en mappen **maken of wijzigen**
> 2. Bestanden en mappen **toevoegen** *(Eng.: to add)* aan de Git-stage
> 3. De wijzigingen **vastleggen** *(Eng.: to commit)* op de lokale computer.
> 4. De gecommitte wijzigingen **duwen** *(Eng.: to push)* naar de GitHub-server.

Alle Bestanden en mappen (`.`) toevoegen (`add`) aan de Git-stage.

{% highlight posh %}
PS> git add .
{% endhighlight %}

De wijzigingen committen (`commit`) met een boodschap *(Eng.: message, `-m`)* die verklaart wat je gedaan hebt sinds de vorige commit.

{% highlight posh %}
PS> git commit -m "Ik heb vanalles gedaan"
{% endhighlight %}

Alle gecommitte wijzigingen pushen naar de GitHub-server.

{% highlight posh %}
PS> git push
{% endhighlight %}

> Tip
> ---
> Je kan de huidige toestand van de Git-stage opvragen met `git status`.
{:.card.card-tip}

GitHub Pages instellen
----------------------

> GitHub
> ---
> Ga naar je repository en open de instellingen.  
> <kbd class="menu"><kbd>Settings</kbd>&#9656;<kbd>GitHub Pages</kbd>&#9656;<kbd>Source</kbd></kbd> moet op `Master Branch` staan 
{:.card.card-github}