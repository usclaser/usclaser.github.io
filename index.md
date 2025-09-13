---
title: "Home"
layout: default
classes: wide
permalink: "/"
---

<div class="col-12 col-lg-10">
        <div class="row my-4">
            <div class="col-12">
                        <div id="projectCarousel" class="carousel slide" data-bs-ride="carousel" data-bs-interval="8000">
                            <div class="carousel-indicators">
                                {% assign research_page = site.pages | where: 'title', 'Research' | first %}
                                {% assign projs = research_page.projects %}
                                {% for p in projs %}
                                    <button type="button" data-bs-target="#projectCarousel" data-bs-slide-to="{{ forloop.index0 }}" class="{% if forloop.first %}active{% endif %}" aria-current="{% if forloop.first %}true{% else %}false{% endif %}" aria-label="Slide {{ forloop.index }}"></button>
                                {% endfor %}
                            </div>
                            <div class="carousel-inner fixed-carousel-height">
                        {% for p in projs %}
                            <div class="carousel-item {% if forloop.first %}active{% endif %}">
                                        <a href="{{ '/research/' | relative_url }}#{{ p.slug }}" class="d-flex justify-content-center align-items-center carousel-image-wrapper">
                                            <img src="{{ p.image | relative_url }}" class="img-fluid" alt="{{ p.title }}">
                                    <div class="carousel-caption d-none d-md-block">
                                        <h5>{{ p.title }}</h5>
                                    </div>
                                </a>
                            </div>
                        {% endfor %}
                    </div>
                    <button class="carousel-control-prev" type="button" data-bs-target="#projectCarousel" data-bs-slide="prev">
                        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                        <span class="visually-hidden">Previous</span>
                    </button>
                    <button class="carousel-control-next" type="button" data-bs-target="#projectCarousel" data-bs-slide="next">
                        <span class="carousel-control-next-icon" aria-hidden="true"></span>
                        <span class="visually-hidden">Next</span>
                    </button>
                </div>
            </div>
        </div>

        <div class="row g-4">
            <div class="col-12">
                <h2>About the Lab</h2>
                {% capture md %}{% include laser.md %}{% endcapture %}
                {{ md | markdownify }}
                <p class="mt-3">
                    Explore our <a href="{{ '/research/' | relative_url }}">research</a> and <a href="{{ '/publications/' | relative_url }}">publications</a>, meet the <a href="{{ '/people/' | relative_url }}">team</a>.
                </p>
            </div>
        </div>

  
</div>
