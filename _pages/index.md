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

I built this website in order to showcase my works and passion. I wrote about projects I made basically about programming and related questions so that people can reach out to me in any case.

I have provided links to my various sites. So use them if necessary and do give them a visit!

<hr/>

### Recent Posts

{% for post in site.posts limit:2 %}
{% include components/post-card.html %}
{% endfor %}

### GitHub contributions

<div class="container calendar">
  <!-- Loading stuff -->
  Loading the data just for you.
</div>

<div class="alert alert-success" role="alert">
  Don't forget to subscribe to my <a target = "_blank" href="https://rocky-mesa-67884.herokuapp.com/" class="alert-link">NewsLetter</a>. Give it a click if you like.
</div>

<script>
  GitHubCalendar(".calendar", "Abdus-Samee", {
    responsive: true,
    tooltips: true
  });
</script>
