---
layout: about
title: About
permalink: /

profile:
  align: right
  image: si-xian-hsu.jpg

social: true
---

I’m a third-year undergraduate in the [Department of **Electrical Engineering**](https://web.ee.ntu.edu.tw/ntuee/) at [National Taiwan University (NTU)](https://www.ntu.edu.tw/english/), pursuing a second major in [**Sociology**](https://sociology.ntu.edu.tw/en/?doing_wp_cron=1714985439.5166759490966796875000). I work as an undergraduate researcher in Prof. [Cheng-Wei Chen](https://scholar.google.com/citations?user=spTwAGcAAAAJ&hl=zh-TW)’s [NASA Lab](https://cwchenee.wixsite.com/nasa-ntuee), where I’m developing an automated tooth-to-robot registration method for a dental surgical robot. My goal is to improve registration accuracy while reducing operator-induced errors and the need for repetitive manual steps.

My research interests lie at the intersection of **reinforcement learning** and **robotics**, particularly how robots can interact reliably with people and how to interpret the relationship between robot and physical world. I’ve sought out research opportunities in both robot learning and applied physics, spending four months in Prof. [Shao-Hua Sun](https://shaohua0116.github.io/)’s [RL Lab](https://nturll.netlify.app/about) reviewing approaches to uncertainty-guided robotic interaction and a year at Academia Sinica’s [Applied Nano-photonics Laboratory (ANPL)](https://sites.google.com/view/rcas-anpl/home) studying nanophotonic structures.

⮕ Check more! [Research and experience]({{ '/cv/#experience' | relative_url }}) · [Projects]({{ '/projects/' | relative_url }}) · [Presentation & Awards]({{ '/publications/' | relative_url }})

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
