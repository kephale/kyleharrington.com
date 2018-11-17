---
layout: page
title: Kyle Harrington's CV
permalink: /cv/
pdf: true
---

Kyle Harrington's CV

<a class="button button-sidebar" title="Download my CV" data-toggle="download-pdf">
      <i class="fas fa-download"></i>
      Resume PDF
    </a>

Job: Testing CV generators

Awards: Excellence!

Generated content:

{% for job in cv.jobs %}
  <div>
    <h3>
      <a href={{ job.company.website }} target="_blank">{{ job.company.name }}</a>
    </h3>

    {% for position in job.positions %}
      <div>
        <span>{{ position.title }}</span>
        <span>({{ position.duration }})</span>
      </div>
    {% endfor %}

    <p>{{ job.description }}</p>

    <ul>
      {% for accomplishment in job.accomplishments %}
        <li>{{ accomplishment }}</li>
      {% endfor %}
    </ul>
  </div>
{% endfor %}

<div hidden id="cvJson">
  {{ site.data.cv | jsonify }}
</div>
