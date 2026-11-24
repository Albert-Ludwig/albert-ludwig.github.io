---
title: Publications
description: "SoGuDiff, a robotics manuscript under review at IEEE Robotics and Automation Letters."
permalink: /publications/
---

{% assign manuscripts = site.publications | where_exp: 'paper', 'paper.review_status' %}
{% if manuscripts.size > 0 %}
<section class="content-section" aria-labelledby="manuscripts">
  <h2 id="manuscripts">Manuscripts under review</h2>
  {% for paper in manuscripts %}
  <article class="entry">
    <h3><a href="{{ paper.url | relative_url }}">{{ paper.title | escape }}</a></h3>
    <p class="entry-meta"><cite>{{ paper.venue | escape }}</cite> · {{ paper.review_status | escape }}</p>
  </article>
  {% endfor %}
</section>
{% endif %}

{% assign publications = site.publications | where_exp: 'paper', 'paper.review_status == nil' | reverse %}
{% if publications.size > 0 %}
<section class="content-section" aria-labelledby="published-work">
  <h2 id="published-work">Published work</h2>
  {% for paper in publications %}
  <article class="entry">
    <h3><a href="{{ paper.url | relative_url }}">{{ paper.title | escape }}</a></h3>
    {% if paper.venue %}<p class="entry-meta"><cite>{{ paper.venue | escape }}</cite>{% if paper.date %} · {{ paper.date | date: '%Y' }}{% endif %}</p>{% endif %}
  </article>
  {% endfor %}
</section>
{% endif %}
