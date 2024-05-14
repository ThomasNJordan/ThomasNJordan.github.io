---
layout: page
title: projects
permalink: /projects/
description: Personal Projects (when I'm not spending hours playing CTFs)
nav: true
nav_order: 3
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">

<!-- Check if site.projects exists and is not empty -->
{% assign projects = site.projects | default: [] %}
{% if projects.size > 0 %}
  {% assign sorted_projects = projects | sort: "importance" %}
  
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
    <div class="container">
      <div class="row row-cols-1 row-cols-md-2">
      {% for project in sorted_projects %}
        {% include projects_horizontal.liquid %}
      {% endfor %}
      </div>
    </div>
  {% else %}
    <div class="row row-cols-1 row-cols-md-3">
      {% for project in sorted_projects %}
        {% include projects.liquid %}
      {% endfor %}
    </div>
  {% endif %}
{% else %}
  <p>No projects found.</p>
{% endif %}
</div>
