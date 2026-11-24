---
title: Research
description: "Research interests and experience in social robot navigation, informative path planning, and industrial robotics."
permalink: /research/
---

My research interests span planning, control, and learning for autonomous robots.

<section class="content-section" aria-labelledby="research-interests">
  <h2 id="research-interests">Research interests</h2>
  {% include academic/research-interests.html %}
</section>

<section class="content-section" aria-labelledby="research-experience">
  <h2 id="research-experience">Research and engineering experience</h2>
  {% assign projects = site.portfolio | sort: 'order' %}
  {% for project in projects %}
  <article class="entry">
    <h3>{{ project.affiliation | escape }}</h3>
    <p>{{ project.summary | escape }}</p>
    <a href="{{ project.url | relative_url }}">{{ project.title | escape }}</a>
  </article>
  {% endfor %}
</section>

<section class="content-section" aria-labelledby="research-figures">
  <h2 id="research-figures">Research figures</h2>
  {% if site.media.research_figures.size > 0 %}
  <div class="media-grid">
    {% for figure in site.media.research_figures %}
    <figure class="research-figure">
      <img src="{{ figure.path | relative_url }}" alt="{{ figure.alt | escape }}" loading="lazy">
      {% if figure.caption %}<figcaption>{{ figure.caption | escape }}</figcaption>{% endif %}
    </figure>
    {% endfor %}
  </div>
  {% else %}
  <p class="media-placeholder">Research figures to be added.</p>
  {% endif %}
</section>
