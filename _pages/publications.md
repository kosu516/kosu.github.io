---
layout: page
permalink: /publications/
title: Presentation & Awards
nav: true
nav_order: 2
---

## Conference presentations

<div class="publications">

{% bibliography %}

</div>

## Awards

{% for award in site.data.cv.cv.sections["Awards and Recognition"] %}
<h3 class="award-title">{{ award.label | escape }}</h3>

{{ award.details }}
{% endfor %}
