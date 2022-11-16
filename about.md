---
layout: dark
title: About
example: "Example text in this variable."
---

this is a about page {{ site.title }} by {{ site.author.name }}.
{{ page.example }}

{% for animal in site.data.animals %}
- The {{ animal.name }} is a {{ animal.size }} animal.
{% endfor %}}

# large animals
{% for animal in site.data.animals %}
 {% if animal.size == "large" %}- <strong style="color: {{animal.color}};">{{ animal.name }}</strong>
 {% else %}-<small>{{ animal.name }}</small>
 {% endif %}
{% endfor %}}

## small animals only
{% assign small_animals = site.data.animals | where: "size","small" %}
{% for animal in small_animals %}
-  {{ animal.name | upcase }} 
{% endfor %}}
