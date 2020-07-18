---
title: My Gallery
show_profile: true
images:
 - /theme/img/avatar.jpg
 - /theme/img/gal1.jpg
 - /theme/img/gal2.jpg
 - /theme/img/gal3.jpg
 - /theme/img/gal4.png
 - /theme/img/dx1.png
 - /theme/img/dx2.png
 - /theme/img/dx3.png
 - /theme/img/dx4.png
 - /theme/img/sc-share1.png
 - /theme/img/sc-share2.png
 - /theme/img/sc-share3.png
---

My collection of gallery. Click more to continue...


<div class="card-columns">
  {% for img in page.images %}
    <div class="card">
      <img class="card-img-top" src="{{ img }}" />
    </div>
  {% endfor %}
</div>
