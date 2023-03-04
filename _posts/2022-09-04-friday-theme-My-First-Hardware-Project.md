---
title: My First Hardware Project!
tags:
  - code
images:
  - /theme/img/hardware1.PNG
  - /theme/img/hardware2.PNG
  - /theme/img/hardware3.PNG
---

<b>Wonder Hand</b> - my first hardware project! I, along with my two other team mates, built this gesture controlled Arduino project for our course
<i>CSE - 316: Microprocessors, Microcontrollers, and Embedded Systems</i>. This was my first time using an Arduino. It was fun doing the project.

<!--more-->

The link to the GitHub repository is [here](https://github.com/Abdus-Samee/CSE-316/tree/main/Project%20-%20Wonder%20Hand).

<div id="carouselExampleControls" class="carousel slide mb-4" data-ride="carousel">
    <div class="carousel-inner">
        {% for img in page.images %}
            <div class="carousel-item {% if forloop.first %}active{% endif %}">
                <img src="{{ img }}" class="d-block w-100" alt="">
            </div>
        {% endfor %}
    </div>
    <a class="carousel-control-prev" href="#carouselExampleControls" role="button" data-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="sr-only">Previous</span>
    </a>
    <a class="carousel-control-next" href="#carouselExampleControls" role="button" data-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="sr-only">Next</span>
    </a>
</div>

A video demonstration is available on [YouTube](https://www.youtube.com/watch?v=clijZMaVgng)
