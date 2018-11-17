---
layout: page
title: Curriculum Vitae
permalink: /cv/
pdf: true
---

{% assign cv = site.data.cv %}

<a class="button button-sidebar" title="Download my CV" data-toggle="download-pdf">
  <i class="fas fa-download"></i>
  Download PDF
</a>

## Education

{% for school in cv.education %}
  <div>
    <b> {{ school.school }} </b> 
    {{ school.graduated }} <br>    
    {{ school.degree }} <br>
  </div>
{% endfor %}
<br>

## Current Position

{% for position in cv.positions %}
  {% if position.current %}
  <div>
    {{ position.title }}, {{ position.time }},<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<b>{{ position.unit }}</b>,<br>
    &nbsp;&nbsp;&nbsp;&nbsp;{{ position.organization }},<br>
    &nbsp;&nbsp;&nbsp;&nbsp;{{ position.location }}<br>
  </div>
  {% endif %}
{% endfor %}

## Positions

{% for position in cv.positions %}
  {% unless position.current %}
  <div>
    {{ position.title }}, {{ position.time }},<br>
    &nbsp;&nbsp;&nbsp;&nbsp;{{ position.unit }},<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<b>{{ position.organization }}</b>,<br>
    &nbsp;&nbsp;&nbsp;&nbsp;{{ position.location }}<br>
  </div>
  {% endunless %}
{% endfor %}

## Awards and Activities


<div hidden id="cvJson">
  {{ site.data.cv | jsonify }}
</div>
