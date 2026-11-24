---
title: Haoran Ji
description: "Haoran Ji is a Mechatronics Engineering undergraduate at McMaster University working on robotics and autonomous systems."
permalink: /
hide_title: true
---

<div class="profile-intro">
  <div>
    <h1 class="page__title">{{ site.name | escape }}</h1>
    <p class="profile-role">{{ site.author.bio | escape }}<br>{{ site.author.employer | escape }}</p>
    <p>I study robotics and autonomous systems, with an interest in how robots learn, plan, and act under uncertainty. My work spans social navigation on mobile robots, environmental sensing and path planning, and industrial robot control.</p>
    <div class="profile-actions">
      <a class="primary-link" href="{{ '/research/' | relative_url }}">Explore my research</a>
      <a href="{{ '/cv/' | relative_url }}">View my CV</a>
    </div>
  </div>
  <div class="profile-portrait">
    {% if site.author.avatar %}
      {% assign portrait_path = site.author.avatar | prepend: '/images/' %}
      <img src="{{ portrait_path | relative_url }}" alt="Portrait of {{ site.author.name | escape }}">
    {% else %}
      <span class="portrait-initials" aria-hidden="true">HJ</span>
      <span class="portrait-label">Portrait to be added</span>
    {% endif %}
  </div>
</div>

<section class="content-section" aria-labelledby="research-interests">
  <h2 id="research-interests">Research interests</h2>
  {% include academic/research-interests.html %}
</section>

{% assign manuscript = site.publications | where: 'featured', true | first %}
{% if manuscript %}
<section class="content-section" aria-labelledby="featured-manuscript">
  <h2 id="featured-manuscript">Featured manuscript</h2>
  <div class="manuscript-preview">
    <p class="entry-meta">{{ manuscript.venue | escape }} · {{ manuscript.review_status | escape }}</p>
    <a href="{{ manuscript.url | relative_url }}">{{ manuscript.title | escape }}</a>
  </div>
</section>
{% endif %}
