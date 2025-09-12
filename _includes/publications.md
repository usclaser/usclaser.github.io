Selected publications are available here. You can also find my latest work on [Google Scholar](https://scholar.google.com/citations?user=msRla_0AAAAJ&hl=en).

{% assign publications_by_year = site.publications | group_by: "year" | reverse %}

{% for year in publications_by_year %}
  <h1>{{ year.name }}</h1>

  <div class="publication-list">
    {% for pub in year.items %}
      <div class="publication-content">
        <img class="publication-image" src="{{ pub.image }}" alt="Image for {{ pub.title }}"/>
        <div class="publication-text">
          <h4>{{ pub.title }}</h4>
          <p><em>{{ pub.authors }}</em><br>
             {{ pub.journal }}, {{ pub.year }}<br>
             {% if pub.link %}
              <a href="{{ pub.link }}">link</a>&nbsp;
             {% endif %}
             {% if pub.doi %}
              <a href="https://doi.org/{{ pub.doi }}">doi</a>&nbsp;
             {% endif %}
             {% if pub.code %}
              <a href="{{ pub.code }}">code</a>&nbsp;
             {% endif %}
             {{ pub.content }}
          </p>
        </div>
      </div>
    {% endfor %}
  </div>
{% endfor %}