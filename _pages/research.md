---
layout: default
permalink: /research/
title: Research
description: "USC LASER research in robotic autonomy; USC Viterbi (RASC, AME/ASTE/ECE)."
projects:
  - slug: rattle
    title: Learning-Augmented Planning and Control
    image: /assets/images/rend.gif
    description: >-
      Infusing learning-based tools into planning and control to improve efficiency and safety under imperfect knowledge.
  - slug: lunar-leader
    title: Safe and Robust Planning
    image: /assets/images/inspection.png
    description: >-
      Providing or enhancing safety guarantees for uncertain dynamical systems, including when new information is revealed online.
  - slug: microgravity-cd
    title: Information- and Perception-Aware Autonomy
    image: /assets/images/explore.gif
    description: >-
      Considering perception, localization, and information gain explicitly in robotic planning.
  - slug: microgravity-cd
    title: Extreme Environment and Space Systems
    image: /assets/images/robots/wally.png
    description: >-
      Autonomy frameworks incorporating the above topic areas for exploration, space, and other extreme environment robotics applications. We are always looking for new, dynamically interesting robotic systems that invite creative algorithmic solutions.
---

## Research

Increasingly capable algorithms are required to take dynamic mobile robots out of the lab and into the field. Operating under challenging conditions with real-world constraints, these robots face situations that are **uncertain**, **unknown**, or **unstructured** with limitations in perception, real-time demands on compute, and often with complex or stochastic dynamics.

LASER develops methods for adaptive decision-making under uncertainty for these systems, drawing from *control theory*, *reinforcement learning*, and *stochastic modeling*, with an emphasis on a "theory to practice” philosophy including field hardware validation: our work has flown on the International Space Station and, in the coming months, to the Moon. Our overarching goal is to make autonomous robotic operations safer and more efficient when human-in-the-loop operation becomes infeasible, risky, or wasteful.

## Active Topic Areas
<!-- Display projects-->
<div class="row pt-2">
  {% assign projs = page.projects %}
  {% for p in projs %}
    <div class="row"><hr /></div>
    <div class="row justify-content-center py-3" id="{{ p.slug }}">
      <div class="col-8 col-md-4 align-items-center my-auto py-3">
        {% if p.video %}
          <video style="width:100%; height:240px; display:block; object-fit:cover;" controls preload="metadata" playsinline poster="{{ p.image | relative_url }}">
            <source src="{{ p.video | relative_url }}" type="video/mp4" />
            Your browser does not support the video tag.
          </video>
          <p class="small mt-2 mb-0">
            Having trouble? <a href="{{ p.video | relative_url }}" target="_blank" rel="noopener">Open video in a new tab</a>
          </p>
        {% else %}
          <img class="img-fluid" style="width:100%; height:240px; object-fit:cover; object-position:center;" src="{{ p.image | relative_url }}" alt="{{ p.title }}" />
        {% endif %}
      </div>
      <div class="col-10 col-md-8 my-auto">
        <p><b>{{ p.title }}</b></p>
        <p>{{ p.description }}</p>
      </div>
    </div>
  {% endfor %}
</div>
