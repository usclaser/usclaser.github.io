---
layout: default
permalink: /publications/
title: Publications
---

## Publications
<p>
  Selected publications are available here. You can also find our latest work on <a href="https://scholar.google.com/citations?user=msRla_0AAAAJ&hl=en" target="_blank" rel="noopener">Google Scholar</a>.
</p>

<div class="col-12 col-lg-10 publications-page">
  {% assign pubs = site.publications | sort: 'year' | reverse %}
  {% assign years = pubs | map: 'year' | uniq %}
  {% for y in years %}
    <h3 class="mt-4">{{ y }}</h3>
    {% assign group = pubs | where: 'year', y %}
    {% for pub in group %}
      <div class="publication-content">
        {% if pub.image %}
          <img class="publication-image" src="{{ pub.image | relative_url }}" alt="{{ pub.title }}" />
        {% endif %}
        <div class="publication-text">
          <h4 class="mb-1"><a href="{{ pub.url | relative_url }}">{{ pub.title }}</a></h4>
          <div class="text-muted small">
            {% if pub.authors %}{{ pub.authors }}{% endif %}
            {% if pub.venue %} — {{ pub.venue }}{% elsif pub.journal %} — {{ pub.journal }}{% endif %}
            {% if pub.year %} ({{ pub.year }}){% endif %}
          </div>
          <div class="mt-2">
            {% if pub.pdf %}<a href="{{ pub.pdf | relative_url }}" target="_blank" rel="noopener">PDF</a>{% endif %}
            {% if pub.doi %}{% if pub.pdf %} · {% endif %}<a href="https://doi.org/{{ pub.doi }}" target="_blank" rel="noopener">DOI</a>{% endif %}
            {% if pub.link %}{% if pub.pdf or pub.doi %} · {% endif %}<a href="{{ pub.link }}" target="_blank" rel="noopener">Link</a>{% endif %}
            {% if pub.code %}{% if pub.pdf or pub.doi or pub.link %} · {% endif %}<a href="{{ pub.code }}" target="_blank" rel="noopener">Code</a>{% endif %}
          </div>
        </div>
      </div>
    {% endfor %}
  {% endfor %}
</div>
