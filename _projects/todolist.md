---
title: Node.js ToDo list app
images:
  - /theme/img/todo1.png
  - /theme/img/todo2.png
  - /theme/img/todo3.png
  - /theme/img/todo4.png
---

## About

A ToDo list node.js app built on localhost backed by a server. It has beautiful user interface which dynamically adds wishes to the list. The current date is also shown at the top. One can also check/uncheck one or more wishes on the list.

## Views

In the following, I tried to attach some pictures of the app  from showing initial list to adding list and checking them. Unfortunately, no repository or link can be provided for this project.

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
