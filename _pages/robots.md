---
layout: default
permalink: /robots/
title: Robots
---

<div class="col-12 col-lg-10 mx-auto">
  <h2>Robots</h2>
  {% assign robots = site.robots | sort: 'order' %}
  {% if robots and robots.size > 0 %}
    <div class="row g-4 mt-2 justify-content-center">
      {% for r in robots %}
        <div class="col-12 col-sm-6">
          <div class="card h-100 robot-card">
            {% assign img = r.image | default: '/assets/images/robots/placeholder.png' %}
            <img class="card-img-top" src="{{ img | relative_url }}" alt="{{ r.name | default: r.title }}" />
            <div class="card-body">
              <h5 class="card-title">{{ r.name | default: r.title }}</h5>
              <p class="card-text">{{ r.content | markdownify }}</p>
            </div>
          </div>
        </div>
      {% endfor %}
    </div>
  {% else %}
    {% assign robot_images = site.static_files | where_exp: 'f', 'f.path contains "/assets/images/robots/"' | slice: 0, 4 %}
    <div class="robot-grid mt-3">
      {% for file in robot_images %}
        <div class="robot-item">
          <img src="{{ file.path | relative_url }}" alt="Robot {{ forloop.index }}" />
        </div>
      {% endfor %}
    </div>
  {% endif %}
</div>
