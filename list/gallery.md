---
title: My Gallery
show_profile: true
images:
 - /portfolio/theme/img/gal1c.jpg
 - /portfolio/theme/img/gal2c.jpg
 - /portfolio/theme/img/gal3.jpg
 - /portfolio/theme/img/gal4c.png
 - /portfolio/theme/img/gal5c.png
---

<style>
 .css-sprite-gal1n
 {
  background:url('/portfolio/theme/img/css-sprite-combined.png') -5px -2px;
  width:501px;height:498px;
  display:inline-block;
 }

 .css-sprite-gal2n
 {
  background:url('/portfolio/theme/img/css-sprite-combined.png') -511px -0px;
  width:500px;height:500px;
  display:inline-block;
 }

 .css-sprite-gal3
 {
  background:url('/portfolio/theme/img/css-sprite-combined.png') -1016px -300px;
  width:200px;height:200px;
  display:inline-block;
 }

 .css-sprite-gal4n
 {
  background:url('/portfolio/theme/img/css-sprite-combined.png') -1221px -125px;
  width:666px;height:375px;
  display:inline-block;
 }

 .css-sprite-gal5n
 {
  background:url('/portfolio/theme/img/css-sprite-combined.png') -1892px -125px;
  width:666px;height:375px;
  display:inline-block;
 }

</style>


My collection of gallery.


<div class="card-columns">
  {% for img in page.images %}
    <div class="card">
      <img class="card-img-top" src="{{ img }}" />
    </div>
  {% endfor %}
</div>
