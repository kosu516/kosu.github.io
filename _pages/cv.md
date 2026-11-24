---
layout: default
permalink: /cv/
title: CV
nav: true
nav_order: 5
cv_pdf: /assets/pdf/si-xian-hsu-cv.pdf
description: Education, research experience, projects, and leadership.
---

<link rel="stylesheet" href="{{ '/assets/css/al-folio-cv.css' | relative_url | bust_file_cache }}">

{% assign cv = site.data.cv.cv %}

<div class="post">
  <header class="post-header">
    <h1 class="post-title">
      {{ page.title }}
      <a class="float-right" href="{{ page.cv_pdf | relative_url }}" target="_blank" rel="noopener noreferrer" aria-label="Open CV (PDF)">
        <i class="fa-solid fa-file-pdf" aria-hidden="true"></i>
      </a>
    </h1>
    <p class="post-description">{{ page.description }}</p>
  </header>

  <div class="cv-with-sidebar">
    <nav class="cv-section-nav" aria-label="CV sections">
      <ul>
        <li><a href="#cv-overview">Contact Information</a></li>
        {% for section in cv.sections %}
          {% assign title = section[0] %}
          <li><a href="#{{ title | slugify }}">{% if title == 'Experience' %}Research Experience{% else %}{{ title }}{% endif %}</a></li>
        {% endfor %}
      </ul>
    </nav>

    <article class="cv cv-section-content">
      <section id="cv-overview" class="card mt-3 p-3">
        <h2 class="card-title font-weight-medium">Contact Information</h2>
        <table class="table table-cv table-sm table-borderless mb-0">
          <tbody>
            <tr>
              <th scope="row" class="p-1 pr-2">Name</th>
              <td class="p-1 pl-2">{{ cv.name | escape }}</td>
            </tr>
            <tr>
              <th scope="row" class="p-1 pr-2">Email</th>
              <td class="p-1 pl-2"><a href="mailto:{{ cv.email }}">{{ cv.email }}</a></td>
            </tr>
          </tbody>
        </table>
      </section>

      {% for section in cv.sections %}
        {% assign title = section[0] %}
        {% assign entries = section[1] %}
        <section id="{{ title | slugify }}" class="card mt-3 p-3">
          <h2 class="card-title font-weight-medium">{% if title == 'Experience' %}Research Experience{% else %}{{ title }}{% endif %}</h2>
          {% case title %}
            {% when 'Education' %}
              {% assign entries = entries | al_cv_sort_by_date %}
              {% include cv/education.liquid %}
            {% when 'Experience' %}
              {% assign entries = entries | al_cv_sort_by_date %}
              {% include cv/experience.liquid %}
            {% else %}
              <ul class="card-text font-weight-light list-group list-group-flush">
                {% for entry in entries %}
                  <li class="list-group-item">
                    {% if title == 'Projects' %}
                      {% assign project = site.projects | where: 'title', entry.name | first %}
                      {% if project %}
                        <a href="{{ project.url | relative_url }}">{{ entry.name | escape }}</a>
                      {% else %}
                        {{ entry.name | escape }}
                      {% endif %}
                    {% elsif title == 'Awards and Recognition' %}
                      <strong>{{ entry.name | escape }}</strong> ·
                      <time datetime="{{ entry.date }}">{{ entry.date | append: '-01' | date: '%b %Y' }}</time>
                      {{ entry.highlights.first | markdownify }}
                    {% elsif entry.bullet %}
                      {{ entry.bullet | markdownify | remove_first: '<p>' | remove: '</p>' }}
                    {% elsif entry.label %}
                      <strong>{{ entry.label | escape }}</strong> · {{ entry.details | escape }}
                    {% endif %}
                  </li>
                {% endfor %}
              </ul>
          {% endcase %}
        </section>
      {% endfor %}
    </article>

  </div>
</div>
