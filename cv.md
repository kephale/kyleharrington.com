---
layout: page
title: Kyle Harrington's CV
permalink: /cv/
pdf: true
---

Kyle Harrington's CV

Job: Testing CV generators

Awards: Excellence!

Testing:

{% for page in site.pages %}
  {% if page.url == '/path/to/page.html' %}
[{{ page.title }}]({{ page.url }})
  {% endif %}
{% endfor %}
