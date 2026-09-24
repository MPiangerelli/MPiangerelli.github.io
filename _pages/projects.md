---
layout: page
title: projects
permalink: /projects/
description: Research and technology-transfer projects, from European FET projects to industrial collaborations, in reverse chronological order.
nav: true
nav_order: 3
horizontal: false
redirect_from:
  - /projects.html
feature_image: /assets/img/headers/balla.jpg
feature_painting: "Forze di paesaggio + cocomero"
feature_author: Giacomo Balla
---

<!-- pages/projects.md -->
<div class="projects">
{% assign sorted_projects = site.projects | sort: "importance" %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
</div>
