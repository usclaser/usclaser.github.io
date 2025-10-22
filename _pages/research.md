---
layout: default
permalink: /research/
title: Research
projects:
  - slug: rattle
    title: Robust model improvement for on-orbit robots (RATTLE)
    image: /assets/images/publications/2022_ral.png
    description: >-
      RATTLE develops a motion planning algorithm that improves parametric models online,
      using real robot data to reduce uncertainty and increase robustness during
      close-proximity operations.
  - slug: lunar-leader
    title: Persistent leader election for multi-robot exploration (Lunar Leader)
    image: /assets/images/publications/2024_aamas.png
    description: >-
      A distributed algorithm for electing a leader that persists under communication
      dropouts and dynamics, enabling coordinated behaviors in challenging environments.
  - slug: microgravity-cd
    title: Change detection in microgravity (AstrobeeCD)
    image: /assets/images/publications/2024_acta.png
    description: >-
      Perception-informed autonomy to detect environmental changes for free-flying
      robots, enabling safer and more reliable task execution on-orbit.
---

## Research

Increasingly capable algorithms are required to continue taking dynamic mobile robots out of the lab and into the field. Operating under challenging conditions with real-world constraints, these robots face situations that are **uncertain**, **unknown**, or **unstructured** with limitations in perception, real-time demands on compute, and often with complex or stochastic dynamics.

LASER develops methods for adaptive decision-making under uncertainty for these systems, drawing from *control theory*, *reinforcement learning*, and *stochastic modeling*, with an emphasis on a "theory to practice” philosophy including field hardware validation: our work has flown on the International Space Station and, in the coming months, to the Moon. Our overarching goal is to make autonomous robotic operations safer and more efficient when human-in-the-loop operation becomes infeasible, risky, or wasteful. To this end, some of our current research areas include:

- Infusing learning-based tools into planning and control to improve efficiency and safety under imperfect knowledge.
- Providing or enhancing safety guarantees for uncertain dynamical systems, including when new information is revealed online.
- Considering perception, localization, and information gain explicitly in robotic planning.
- Autonomy frameworks incorporating the above for exploration, space, and other extreme environment robotics applications.
<!-- Display projects-->
<div class="row pt-2">
  {% assign projs = page.projects %}
  {% for p in projs %}
    <div class="row">
      <hr />
    </div>
    <div class="row justify-content-center py-3" id="{{ p.slug }}">
      <div class="col-8 col-md-4 align-items-center my-auto py-3">
        <img class="img-fluid" src="{{ p.image | relative_url }}" alt="{{ p.title }}" />
      </div>
      <div class="col-10 col-md-8 my-auto">
        <p><b>{{ p.title }}</b></p>
        <p>{{ p.description }}</p>
      </div>
    </div>
  {% endfor %}
</div>
