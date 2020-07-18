---
title: My Gallery
show_profile: true
thumbnail:
 - /portfolio/theme/img/avatar.jpg
 - /portfolio/theme/img/gal1.jpg
 - /portfolio/theme/img/gal2.jpg
 - /portfolio/theme/img/gal3.jpg
 - /portfolio/theme/img/gal4.png
 - /portfolio/theme/img/gal5.png
 - /portfolio/theme/img/dx1.png
 - /portfolio/theme/img/dx2.png
 - /portfolio/theme/img/dx3.png
 - /portfolio/theme/img/dx4.png
 - /portfolio/theme/img/sc-share1.png
 - /portfolio/theme/img/sc-share2.png
 - /portfolio/theme/img/sc-share3.png
---

My collection of gallery.


<div class="card-columns">
  {% for img in page.thumbnail %}
    <div class="card">
      <img class="card-img-top" src="{{ img }}" />
    </div>
  {% endfor %}
</div>
