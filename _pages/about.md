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

I’m a third-year undergraduate at National Taiwan University (NTU), majoring in Electrical Engineering and pursuing a second major in Sociology. I work as an undergraduate researcher in Prof. Cheng-Wei Chen’s NASA Lab, where I’m developing an automated tooth-to-robot registration method for a dental surgical robot. My goal is to improve registration accuracy while reducing operator-induced errors and the need for repetitive manual steps.

My research interests lie at the intersection of reinforcement learning and robotics, particularly how robots can interact reliably with people and how to interpret the relationship between robot and physical world. I’ve sought out research opportunities in both robot learning and applied physics, spending four months in Prof. Shao-Hua Sun’s RL Lab reviewing approaches to uncertainty-guided robotic interaction and a year at Academia Sinica’s Applied Nano-photonics Laboratory (ANPL) studying nanophotonic structures.

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
