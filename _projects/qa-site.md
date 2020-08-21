---
title: A Dynamic Q/A site
images:
  - /portfolio/theme/img/stack1.png
  - /portfolio/theme/img/stack2.png
  - /portfolio/theme/img/stack3.png
  - /portfolio/theme/img/stack4.png
  - /portfolio/theme/img/stack5.png
---

It is a backend supported website I created as a copy of [Stack Overflow](https://stackoverflow.com/). It is a Q/A site, supported by user authorization.

<!--more-->

## Views

In the following, I attached some screenshots of the website. A user can login if needed. Otherwise, the user cannot ask/answer any question, but can view them. A profile page is also attahced for every user upon logging in. I tried to implement session, authorization, database, custom routes for each posts, search options and many more in this project. However, the styling may seem bland as I've focused more on the backend. But I tried to keep it simple and make it a responsive site.

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

## More

The link to the website is [here](http://stack-overflow-forum.herokuapp.com). A GitHub repository has not been created yet.
