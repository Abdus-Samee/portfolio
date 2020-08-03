---
title: Screen sharing between two PCs using Java
images:
  - /portfolio/theme/img/sc-share1.png
  - /portfolio/theme/img/sc-share2.png
  - /portfolio/theme/img/sc-share3.png
---

This is a project I developed using Java and its library JavaFX. In this program, there is a single server and a single client. It is at the time being a one-way communication. I will try my utmost to develop this into a two-way screen sharing. In addition, I will try to enable remote desktop control via mouse click too.

<!--more-->

## Views

Below are some still pictures of the project in sequential order. I tried to show the window of the server receiving continuous screen images from the client. Here, the client screen is shown at first, but minimized later on. Moreover, this project has been done on localhost. So the view looked so repetitive.

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

The link to the GitHub repository of this project is [here](https://github.com/Abdus-Samee/ScreenShare). You can download the zip of the folder or git it. Remember, you have to start the server before the client in order for the project to work. Last but not the least, openjdk-14 was used here. So be sure to check the project structure and the configuration before running the program.
