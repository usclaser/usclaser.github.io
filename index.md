---
title:  "home"
layout: default
classes: wide
permalink: "/"
---

<div class="col-10 col-lg-6">
    <div class="row justify-content-center my-2">
        <div class="col-12 bio">
            {% capture md %}{% include keenan.md %}{% endcapture %}
            {{ md | markdownify }}
        </div>
    </div>
    <hr />
    <div class="row justify-content-center links text-center my-2">
        <div class="col-auto">
            <a data-target="research" class="content-button">Research</a>
        </div>
        <div class="col-auto">
            <a data-target="about" class="content-button">About</a>
        </div>
        <div class="col-auto">
            <a data-target="cv" class="content-button" href="./assets/pdfs/keenan_albee_cv.pdf">CV</a>
        </div>
        <div class="col-auto">
            <a data-target="laser" class="content-button">LASER</a>
        </div>       
    </div>
    <hr/>
    <div class="row justify-content-center">
        <div class="col-12">
            <div id="research-container" class="content-section d-none">
              {% capture md %}{% include publications.md %}{% endcapture %}
              {{ md | markdownify }}
            </div>
            <div id="about-container" class="content-section d-none">
              {% capture md %}{% include about.md %}{% endcapture %}
              {{ md | markdownify }}
            </div>
            <div id="laser-container" class="content-section d-none">
              {% capture md %}{% include laser.md %}{% endcapture %}
              {{ md | markdownify }}
            </div>
        </div>
    </div>
</div>
