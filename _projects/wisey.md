---
title: NodeJS backend project with authorization
images:
  - /portfolio/theme/img/wisey1.png
  - /portfolio/theme/img/wisey2.png
  - /portfolio/theme/img/wisey3.png
  - /portfolio/theme/img/wisey4.png
---

This is my first project on backend with NodeJS. I tried to incorporate the things I learn like templates, views, routing, mongodb database, authorization, session, cookies and 
related stuff. I deployed this site on heroku. 

<!--more-->

## Views

On this site, a user can login or signup. It would redirect the user to the main page. There the user can view my wise words. The user can also comment there. Last but not the
least, there is a logout system which would expire the current session of the user. He/She cannot go to the main route without logging again. Cookies are also enabled. Some 
still cuts are as follows:

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

There is currently no GitHub repository. But you could visit the site [here](http://wisey-word.herokuapp.com).
