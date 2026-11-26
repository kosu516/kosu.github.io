---
layout: default
permalink: /cv/
title: Curriculum Vitae
nav: true
nav_order: 5
cv_pdf: /assets/pdf/si-xian-hsu-cv.pdf
description: This is Si-Xian's CV. Check the PDF file for more details!
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
        {% if title == 'Education' or title == 'Experience' %}
          {% assign entries = entries | al_cv_sort_by_date %}
        {% endif %}
        <section id="{{ title | slugify }}" class="card mt-3 p-3">
          <h2 class="card-title font-weight-medium">{% if title == 'Experience' %}Research Experience{% else %}{{ title }}{% endif %}</h2>
          <ul class="card-text font-weight-light list-group list-group-flush">
            {% for entry in entries %}
              {% if entry.start_date or entry.date %}
                {% assign start = entry.start_date | default: entry.date %}
                {% assign entry_title = entry.position | default: entry.degree | default: entry.name %}
                {% assign organization = entry.company | default: entry.institution %}
                <li class="list-group-item cv-dated-entry">
                  <span class="badge font-weight-bold text-uppercase cv-date">
                    <time datetime="{{ start }}">{{ start | append: '-01' | date: '%b %Y' }}</time>
                    {% if entry.end_date == 'present' %}
                      – Present
                    {% elsif entry.end_date %}
                      – <time datetime="{{ entry.end_date }}">{{ entry.end_date | append: '-01' | date: '%b %Y' }}</time>
                    {% endif %}
                  </span>
                  <h3 class="cv-entry-title">
                    {% if entry.url %}<a href="{{ entry.url }}">{{ entry_title | escape }}</a>{% else %}{{ entry_title | escape }}{% endif %}
                  </h3>
                  <div class="cv-entry-details">
                    {% if organization %}
                      <p>{{ organization | escape }}{% if entry.location %}, {{ entry.location | escape }}{% endif %}</p>
                    {% endif %}
                    {% if entry.area %}
                      <p><em>{{ entry.area | escape }}</em></p>
                    {% endif %}
                    {% if title == 'Awards and Recognition' %}
                      {{ entry.highlights.first | markdownify }}
                    {% elsif entry.highlights %}
                      <ul>
                        {% for item in entry.highlights %}
                          <li>{{ item | markdownify | remove_first: '<p>' | remove: '</p>' }}</li>
                        {% endfor %}
                      </ul>
                    {% endif %}
                  </div>
                </li>
              {% else %}
                <li class="list-group-item">
                  {% if title == 'Projects' %}
                    {% assign project = site.projects | where: 'title', entry.name | first %}
                    {% if project %}
                      <a href="{{ project.url | relative_url }}">{{ entry.name | escape }}</a>
                    {% else %}
                      {{ entry.name | escape }}
                    {% endif %}
                  {% elsif entry.bullet %}
                    {{ entry.bullet | markdownify | remove_first: '<p>' | remove: '</p>' }}
                  {% elsif entry.label %}
                    <strong>{{ entry.label | escape }}</strong> · {{ entry.details | escape }}
                  {% endif %}
                </li>
              {% endif %}
            {% endfor %}
          </ul>
        </section>
      {% endfor %}
    </article>

  </div>
</div>
