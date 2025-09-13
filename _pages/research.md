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

<div class="col-12 col-lg-10">
  <h2>Research Themes</h2>
  {% capture md %}{% include research.html %}{% endcapture %}
  {{ md | markdownify }}

  <h3 class="mt-4">Current Projects</h3>
  <ul>
    <li>Risk-aware motion planning and control under uncertainty</li>
    <li>Perception-informed planning for extreme environments</li>
    <li>Multi-robot autonomy for space and field robotics</li>
  </ul>

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
</div>
