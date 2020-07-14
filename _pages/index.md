---
layout: defaults/page
permalink: index.html
narrow: true
title: Welcome to my Website
---

## Introduction

I built this website in order to showcase my works and passion. I wrote about projects I made basically about programming and related questions so that people can reach out to me in any case.

I have provided links to my various sites. So use them if necessary and do give them a visit!

<hr/>

### Recent Posts

{% for post in site.posts limit:2 %}
{% include components/post-card.html %}
{% endfor %}

<h2 class = "display-2"> Attention !</h2>
<div class="alert alert-success" role="alert">
  Don't forget to subscribe to my <a target = "_blank" href="https://rocky-mesa-67884.herokuapp.com/" class="alert-link">NewsLetter</a>. Give it a click if you like.
</div>
