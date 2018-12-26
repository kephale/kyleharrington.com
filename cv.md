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
    &nbsp;&nbsp;&nbsp;&nbsp;{{ school.degree }} <br>
  </div>
{% endfor %}
<br>

## Current Position

{% for position in cv.positions %}
  {% if position.current %}
  <div>
    {{ position.title }}, {{ position.time }},<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<b>{{ position.unit }}</b>,<br>
    &nbsp;&nbsp;&nbsp;&nbsp;{{ position.organization }},
    {{ position.location }}<br>
  </div>
  {% endif %}
{% endfor %}
<br>

## Positions

{% for position in cv.positions %}
  {% unless position.current %}
  <div>
    {{ position.title }}, {{ position.time }},<br>
    &nbsp;&nbsp;&nbsp;&nbsp;{{ position.unit }},<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<b>{{ position.organization }}</b>,
    {{ position.location }}<br>
  </div>
  {% endunless %}
{% endfor %}
<br>

## Awards and Activities

{% for aa in cv.awards_activities %}
  <div>
    {{ aa.time }}, {{ aa.title }}<br>
  </div>
{% endfor %}
<br>

## Reviewing

**Journals:**
{% for journal in cv.reviewing.publications %}
  <div>
    {{ journal }}<br>
  </div>
{% endfor %}
<br>

**Grants:**
{% for agency in cv.reviewing.grants %}
  <div>
    {{ agency }}<br>
  </div>
{% endfor %}
<br>

## Publications

{% assign pubs = site.data.bibliography.references  %}

{% for pub in pubs %}
  <div>
    {% assign issued = pub.issued %}
    {{ issued }}, {{ pub.title }}<br>
  </div>
{% endfor %}
<br>


<div hidden id="cvJson">
  {{ site.data.cv | jsonify }}
</div>
