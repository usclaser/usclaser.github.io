---
layout: default
permalink: /people/
title: People
---

<div class="col-12 col-lg-10">
  <h2>People</h2>
  <p>We are growing the LASER team. Current members are listed below.</p>

  <div class="row g-4">
    {% assign folks = site.people | sort: 'order' %}
    {% for person in folks %}
      <div class="col-12 col-md-6">
        <div class="card h-100">
          {% if person.image %}
            <img src="{{ person.image | relative_url }}" class="card-img-top" alt="{{ person.name }}"/>
          {% endif %}
          <div class="card-body">
            <h5 class="card-title">{{ person.name }}</h5>
            <p class="card-text">{{ person.role }}</p>
            <p class="card-text">{{ person.content | markdownify }}</p>
            <p class="card-text">
              {% if person.email %}<a href="mailto:{{ person.email }}">email</a>{% endif %}
              {% if person.website %} / <a href="{{ person.website }}">website</a>{% endif %}
            </p>
          </div>
        </div>
      </div>
    {% endfor %}
  </div>
</div>
