{% assign workload = site.data.syllabus.workload %}
De studieomvang bedraagt **{{ workload.credits }} studiepunten**{:.label.label-{{ site.colour }}} volgens het [European Credit Transfer and Accumulation System][ECTS].

| Activiteit | Uur  |
|:-----------|-----:|
{% assign total = 0 %}{% for hour in workload.hours %}{% for item in hour %}| {{ item[0] }} | {{ item[1] }} |{% assign total = total | plus: item[1] %}{% endfor %}
{% endfor %}|=|=|
| **Totaal** | **{{ total }}** |
{:.table}

{% include components/pie-chart.html %}

> ##### **Tip** :bulb:
> ---
> Concreet wordt van elke student verwacht dat hij/zij **individueel minstens {{ workload.time.commitment }}** aan deze opdracht besteedt.
> Dit is vergelijkbaar met **{{ workload.time.equivalent }} fulltime** werken.
{:.alert.alert-info}
