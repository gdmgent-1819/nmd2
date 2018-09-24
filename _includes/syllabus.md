{% comment %}
<!-- ⚓ Afkortingen -->
{% endcomment %}
*[{{ site.title }}]:                                {{ site.data.syllabus.title.full }}
{% if site.data.syllabus.programme.minor %}
*[{{ site.data.syllabus.programme.minor.short }}]:  {{ site.data.syllabus.programme.minor.full }}
{% endif %}

{% comment %}
<!-- ⚓ Hyperlinks -->
{% endcomment %}
{% for author in site.data.syllabus.authors %}
[{{ author.name.full }}]: {{ author.website }}
{% endfor %}
[Chamilo]:                                          http://chamilo.arteveldehs.be/index.php?application=weblcms&course={{ site.data.syllabus.course.chamilo_id }}&tool=document&go=course_viewer
[ECTS-fiche]:                                       {{ site.data.syllabus.course.ects_fiche }}