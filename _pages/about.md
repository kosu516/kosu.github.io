---
layout: about
title: About
permalink: /
subtitle: Electrical Engineering Undergraduate · National Taiwan University

profile:
  align: right
  image: si-xian-hsu.jpg

social: true
---

TBD

[Research and experience]({{ '/cv/#experience' | relative_url }}) · [Projects]({{ '/projects/' | relative_url }}) · [Presentation & Awards]({{ '/publications/' | relative_url }})

## News

<ul class="home-news">
  {% for update in site.data.news %}
    <li>
      <time datetime="{{ update.date }}">{{ update.date | append: '-01' | date: '%b %Y' }}</time>
      <span>
        {{ update.text | markdownify | remove_first: '<p>' | remove: '</p>' | strip }}
        {% if update.url %}<a href="{{ update.url | relative_url }}">{{ update.link_text }}</a>{% endif %}
      </span>
    </li>
  {% endfor %}
</ul>
