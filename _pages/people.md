---
layout: default
permalink: /people/
title: People
---

<div class="col-12 col-lg-10">
  <h2>People</h2>
  {% assign members = site.people | sort: 'order' %}

  {% assign leadership = members | where_exp: 'p', 'p.group == "leadership" or p.category == "leadership"' %}
  {% assign students = members | where_exp: 'p', 'p.group == "students" or p.category == "students"' %}
  {% assign alumni = members | where_exp: 'p', 'p.group == "alumni" or p.category == "alumni"' %}

  {% if leadership and leadership.size > 0 %}
    <h3 class="mt-4">Leadership</h3>
    <div class="row g-4">
      {% for p in leadership %}
        <div class="col-12 col-sm-6 col-md-4 col-lg-3">
          <div class="card h-100">
            {% assign img = p.image | default: '/assets/images/robot.png' %}
            <img class="card-img-top" src="{{ img | relative_url }}" alt="{{ p.name | default: p.title }}" />
            <div class="card-body">
              <h5 class="card-title mb-1">{{ p.name | default: p.title }}</h5>
              {% if p.role %}<div class="text-muted small mb-2">{{ p.role }}</div>{% endif %}
              <div class="card-text">{{ p.content | markdownify }}</div>
            </div>
          </div>
        </div>
      {% endfor %}
    </div>
  {% endif %}

  {% if students and students.size > 0 %}
    <h3 class="mt-4">Students</h3>
    <div class="row g-4">
      {% for p in students %}
        <div class="col-12 col-sm-6 col-md-4 col-lg-3">
          <div class="card h-100">
            {% assign img = p.image | default: '/assets/images/robot.png' %}
            <img class="card-img-top" src="{{ img | relative_url }}" alt="{{ p.name | default: p.title }}" />
            <div class="card-body">
              <h5 class="card-title mb-1">{{ p.name | default: p.title }}</h5>
              {% if p.role %}<div class="text-muted small mb-2">{{ p.role }}</div>{% endif %}
              <div class="card-text">{{ p.content | markdownify }}</div>
            </div>
          </div>
        </div>
      {% endfor %}
    </div>
  {% endif %}

  {% if alumni and alumni.size > 0 %}
    <h3 class="mt-4">Alumni</h3>
    <div class="row g-4">
      {% for p in alumni %}
        <div class="col-12 col-sm-6 col-md-4 col-lg-3">
          <div class="card h-100">
            {% assign img = p.image | default: '/assets/images/robot.png' %}
            <img class="card-img-top" src="{{ img | relative_url }}" alt="{{ p.name | default: p.title }}" />
            <div class="card-body">
              <h5 class="card-title mb-1">{{ p.name | default: p.title }}</h5>
              {% if p.role %}<div class="text-muted small mb-2">{{ p.role }}</div>{% endif %}
              <div class="card-text">{{ p.content | markdownify }}</div>
            </div>
          </div>
        </div>
      {% endfor %}
    </div>
  {% endif %}

  <h3 class="mt-4">Team</h3>
  <div class="row g-4">
    {% for p in members %}
      {% unless p.group == 'leadership' or p.category == 'leadership' or p.group == 'students' or p.category == 'students' or p.group == 'alumni' or p.category == 'alumni' %}
        <div class="col-12 col-sm-6 col-md-4 col-lg-3">
          <div class="card h-100">
            {% assign img = p.image | default: '/assets/images/robot.png' %}
            <img class="card-img-top" src="{{ img | relative_url }}" alt="{{ p.name | default: p.title }}" />
            <div class="card-body">
              <h5 class="card-title mb-1">{{ p.name | default: p.title }}</h5>
              {% if p.role %}<div class="text-muted small mb-2">{{ p.role }}</div>{% endif %}
              <div class="card-text">{{ p.content | markdownify }}</div>
            </div>
          </div>
        </div>
      {% endunless %}
    {% endfor %}
  </div>
</div>
