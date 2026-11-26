---
layout: page
permalink: /publications/
title: Presentation & Awards
nav: true
nav_order: 2
---

## Conference presentations

<div class="publications conference-presentations">

{% capture presentations %}{% bibliography %}{% endcapture %}
{% assign pose_guided_author_line = '(id="lin2025poseguided"[^>]*>[\s\S]*?<div class="author">[\s\S]*?)(\s*</div>)' %}
{{ presentations | regex_replace: pose_guided_author_line, '\1 (equally contribution)\2' }}

</div>

## Awards

{% assign awards_by_year = site.data.cv.cv.sections["Awards and Recognition"] | group_by_exp: "award", "award.date | slice: 0, 4" | sort: "name" | reverse %}

<div class="publications">
  {% for year in awards_by_year %}
    <h2 class="bibliography">{{ year.name }}</h2>
    <ol class="bibliography">
      {% for award in year.items %}
        <li>
          <div class="title">{{ award.name | escape }}</div>
          {{ award.highlights.first | markdownify }}
        </li>
      {% endfor %}
    </ol>
  {% endfor %}
</div>
