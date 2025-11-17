---
layout: default
permalink: /people/
title: People
description: "Meet USC LASER — faculty, students at the University of Southern California (RASC, AME/ASTE/ECE)."
---

<div class="col-12 col-lg-10 people-page">
  <h2>People</h2>
  {% assign members = site.people | sort: 'order' %}

  {% assign pi = members | where_exp: 'p', 'p.group == "pi" or p.category == "pi"' %}
  {% assign team = members | where_exp: 'p', 'p.group == "team" or p.category == "team"' %}
  {% assign alumni = members | where_exp: 'p', 'p.group == "alumni" or p.category == "alumni"' %}

  {% if pi and pi.size > 0 %}
    <h3 class="mt-4">Principal Investigator</h3>
    {% for p in pi %}
      <div class="row g-4 align-items-start mb-4">
        <div class="col-12 col-lg-6 pi-figure">
          {% if p.images %}
            {% for im in p.images %}
              <img src="{{ im | relative_url }}" alt="{{ p.name | default: p.title }}" class="img-fluid mb-3" />
            {% endfor %}
          {% elsif p.image %}
            <img src="{{ p.image | relative_url }}" alt="{{ p.name | default: p.title }}" class="img-fluid mb-3" />
          {% else %}
            <img src="{{ '/assets/images/robots/laser_r.png' | relative_url }}" alt="{{ p.name | default: p.title }}" class="img-fluid mb-3" />
          {% endif %}
        </div>
        <div class="col-12 col-lg-6">
          <h4 class="mb-1">{{ p.name | default: p.title }}</h4>
          {% if p.role %}<div class="text-muted small mb-2">{{ p.role }}</div>{% endif %}
          <div>{{ p.content | markdownify }}</div>
        </div>
      </div>
    {% endfor %}
  {% endif %}

  {% if team and team.size > 0 %}
    <h3 class="mt-4">Team</h3>
    <div class="row g-4">
      {% for p in team %}
        <div class="col-12 col-sm-6 col-md-4 col-lg-3">
          <div class="card h-100">
            {% assign img = p.image | default: '/assets/images/robots/laser_r.png' %}
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
</div>
