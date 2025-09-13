---
layout: default
permalink: /publications/
title: Publications
---

<div class="col-12 col-lg-10">
  <h2>Publications</h2>
  {% capture md %}{% include publications.md %}{% endcapture %}
  {{ md | markdownify }}
</div>
