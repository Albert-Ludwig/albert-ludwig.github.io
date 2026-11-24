---
title: Projects
description: "Robotics projects in diffusion-based social navigation, environmental field reconstruction, and Delta robot control."
permalink: /projects/
---

{% assign projects = site.portfolio | sort: 'order' %}
<ul class="project-list">
  {% for project in projects %}
  <li class="entry">
    <h2><a href="{{ project.url | relative_url }}">{{ project.title | escape }}</a></h2>
    <p class="entry-meta">{{ project.affiliation | escape }}</p>
    <p>{{ project.summary | escape }}</p>
  </li>
  {% endfor %}
</ul>

<section class="content-section" aria-labelledby="project-videos">
  <h2 id="project-videos">Project videos</h2>
  {% if site.media.project_videos.size > 0 %}
  <div class="media-grid">
    {% for video in site.media.project_videos %}
    <article class="project-video">
      <h3>{{ video.title | escape }}</h3>
      <video controls playsinline preload="metadata" src="{{ video.path | relative_url }}"{% if video.poster %} poster="{{ video.poster | relative_url }}"{% endif %}>
        {% if video.captions %}
        <track kind="captions" src="{{ video.captions | relative_url }}" srclang="en" label="English">
        {% endif %}
      </video>
      <a href="{{ video.path | relative_url }}">Open {{ video.title | escape }} video</a>
    </article>
    {% endfor %}
  </div>
  {% else %}
  <p class="media-placeholder">Project videos to be added.</p>
  {% endif %}
</section>
