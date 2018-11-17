---
layout: page
title: Kyle Harrington's CV
permalink: /cv/
pdf: true
---

Kyle Harrington's CV

Job: Testing CV generators

Awards: Excellence!

Testinggg:

{% for page in site.pages %}
  {% if page.url == '/cv/' %}
[{{ page.title }}]({{ page.pdf_url }})
  {% endif %}
{% endfor %}
