
{% for section in site.data.docs.crud -%}
{% if section.name == include.filename -%}
{% for file in section.files -%}
<article class="docs-article">
<section class="docs-section" markdown="1">
{% include docs/crud/{{ section.name }}/{{ file }}.md %}
</section>
</article>
{% endfor %}
{% endif -%}
{% endfor -%}


