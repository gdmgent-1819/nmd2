{% assign syllabus = site.data.syllabus %}

Welkom op de digitale syllabus van {% if syllabus.type == 'OLOD' %}het OLOD{% elsif syllabus.type == 'MODULE' %}de module{% endif %} **{{ syllabus.title.short }}**!

Deze syllabus bevat een introductie tot de te kennen werkwijze en technologieën, met daarnaast tips, koppelingen naar documentatie, artikelen en tutorials die je op weg helpen bij de zelfstudie. Het is zeker niet de bedoeling dat deze syllabus alle leerstof bevat, maar wel om je richting te geven bij zelfstudie.

Veel studieplezier tijdens deze boeiende ontdekkingstocht!  
De docenten {{ syllabus.title.short }}.

> ##### Citaat :loudspeaker:
> ---
>
> #### "Practice is the best of all instructors."
>
> &mdash; **Publilius Syrus** (Romeins schrijver en moralist)
{:.card.card-block}

| {{ syllabus.title.short }} | Informatie |
|---------------------------:|:-----------|
| {% if syllabus.type == 'OLOD' %}Opleidingsonderdeel{% elsif syllabus.type == 'MODULE' %}Module{% endif %} | {{ syllabus.title.full }} |
| Academiejaar | {{ syllabus.copyright.year }} |
{% for author in syllabus.authors %}| {% if forloop.first %} Verantwoordelijke docent {% else %} Docent {% endif %} | [{{ author.name.full }}][] |
{% endfor %}| Onderwijsinstelling | [{{ syllabus.copyright.institute.nl }}][] |
| Opleiding | {{ syllabus.programme.degree.nl }} |{% if syllabus.programme.major %}
| Afstudeerrichting | {{ syllabus.programme.major.nl }} |{% endif %}{% if syllabus.programme.minor %}
| Keuzeoptie | {{ syllabus.programme.minor.short }} |{% endif %}
{:.table}


{% include afkortingen-computer.md %}
{% include afkortingen-onderwijs.md %}
{% include hyperlinks.md %}
{% include syllabus.md %}