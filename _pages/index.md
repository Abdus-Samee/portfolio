---
layout: defaults/page
permalink: index.html
narrow: true
title: Welcome to my Website
---

<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-172779941-1"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'UA-172779941-1');
</script>

<script src="https://unpkg.com/github-calendar@latest/dist/github-calendar.min.js"></script>
<link rel="stylesheet" href="https://unpkg.com/github-calendar@latest/dist/github-calendar-responsive.css"/>

## Introduction

Hello. This is Abdus Samee. I’m pursuing my B.Sc. degree from the [Department of Computer Science & Engineering, Bangladesh Engineering & Technology(BUET)](https://cse.buet.ac.bd/). I’m a senior and currently in the last semester(8th).

I have provided links to my various sites. Do give them a visit!

<hr/>

### Recent Posts

{% for post in site.posts limit:2 %}
{% include components/post-card.html %}
{% endfor %}

<!-- <div class="alert alert-success" role="alert">
  Don't forget to subscribe to my <a target = "_blank" href="https://rocky-mesa-67884.herokuapp.com/" class="alert-link">NewsLetter</a>. Give it a click if you like.
</div> -->
