---
title: "Home"
layout: default
classes: wide
permalink: "/"
hero_image: /assets/images/splash.png
---

<div class="col-12 col-lg-10 mx-auto">
        <div class="row my-4">
            <div class="col-12 section-veil">
                        <div id="projectCarousel" class="carousel slide mx-auto" data-bs-ride="carousel" data-bs-interval="8000">
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
</div>

<div class="row mt-5">
  <div class="col-12 p-0">
    <section class="full-bleed-band">
      <div class="container">
        <div class="row align-items-start g-4">
          <div class="col-12 col-lg-6">
            <h2>Contact</h2>
            <p>Email: <a href="mailto:{{ site.email }}">{{ site.email }}</a></p>
            <p>USC Viterbi School of Engineering, Los Angeles, CA</p>
          </div>
          <div class="col-12 col-lg-6">
            <div class="ratio ratio-16x9">
              <iframe
                src="https://www.google.com/maps?q=USC%20Viterbi%20School%20of%20Engineering&output=embed"
                style="border:0;" allowfullscreen="" loading="lazy"
                referrerpolicy="no-referrer-when-downgrade"></iframe>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</div>
