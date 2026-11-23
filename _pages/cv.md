---
layout: default
permalink: /cv/
title: CV
nav: true
nav_order: 5
cv_pdf: /assets/pdf/si-xian-hsu-cv.pdf
cv_format: rendercv
description: Education, research experience, projects, and leadership.
---

<link rel="stylesheet" href="{{ '/assets/css/al-folio-cv.css' | relative_url | bust_file_cache }}">

{% assign sections = site.data.cv.cv.sections %}

<div class="cv-with-sidebar">
  <nav class="cv-section-nav" aria-label="CV sections">
    <ul>
      <li><a href="#cv-overview">Contact Information</a></li>
      {% if sections.Experience.size > 0 %}
        <li><a href="#experience">Experience</a></li>
      {% endif %}
      {% for section in sections %}
        {% unless section[0] == 'Experience' or section[0] == 'Volunteer' %}
          <li><a href="#{{ section[0] | slugify }}">{{ section[0] }}</a></li>
        {% endunless %}
      {% endfor %}
    </ul>
  </nav>
  <div id="cv-overview" class="cv-section-content">
    {% al_folio_cv_render %}
  </div>
</div>
