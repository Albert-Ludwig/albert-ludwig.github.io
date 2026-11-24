---
title: CV
description: "Curriculum vitae and academic profile of Johnson Ji."
permalink: /cv/
---

<section class="content-section" aria-labelledby="education">
  <h2 id="education">Education</h2>
  <p><strong>{{ site.author.employer | escape }}</strong><br>{{ site.author.bio | escape }}</p>
</section>

<section class="content-section" aria-labelledby="experience">
  <h2 id="experience">Experience</h2>
  {% assign projects = site.portfolio | sort: 'order' %}
  <ul>
    {% for project in projects %}
    <li><a href="{{ project.url | relative_url }}">{{ project.affiliation | escape }}</a></li>
    {% endfor %}
  </ul>
</section>

<section class="content-section" aria-labelledby="cv-pdf">
  <h2 id="cv-pdf">CV PDF</h2>
  {% if site.media.cv_pdf %}
  <p><a class="primary-link" href="{{ site.media.cv_pdf | relative_url }}" download>Download CV (PDF)</a></p>
  {% else %}
  <p class="media-placeholder">CV PDF to be added.</p>
  {% endif %}
</section>
