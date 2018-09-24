{% comment %}
<!-- ⚓ Afkortingen -->
{% endcomment %}
*[{{ site.title }}]:                            {{ site.data.olod.title.full }}
*[{{ site.data.olod.programme.minor.short }}]:  {{ site.data.olod.programme.minor.full }}

{% comment %}
<!-- ⚓ Hyperlinks -->
{% endcomment %}
{% for author in site.data.olod.authors %}
[{{ author.name.full }}]: {{ author.website }}
{% endfor %}
[Chamilo]:                                      http://chamilo.arteveldehs.be/index.php?application=weblcms&course={{ site.data.olod.course.chamilo_id }}&tool=document&go=course_viewer
[ECTS-fiche]:                                   {{ site.data.olod.course.ects_fiche }}