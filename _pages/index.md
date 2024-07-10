---
layout: defaults/page
permalink: index.html
narrow: true
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

Hello. This is Abdus Samee. I have obtained B.Sc. degree from the [Department of Computer Science & Engineering, Bangladesh Engineering & Technology(BUET)](https://cse.buet.ac.bd/). I am currently working as a Junior Software Engineer at [WSD](https://wsd.com/). I am a member of the Documents team from London and working on structured documents. I also like academics. My research interests are *Federated Learning*, *Human-Computer Interaction*, and *Software Engineering*.

I have provided links to my various sites. Do give them a visit!

<hr/>

### Recent Posts

{% for post in site.posts limit:2 %}
{% include components/post-card.html %}
{% endfor %}

<!-- <div class="alert alert-success" role="alert">
  Don't forget to subscribe to my <a target = "_blank" href="https://rocky-mesa-67884.herokuapp.com/" class="alert-link">NewsLetter</a>. Give it a click if you like.
</div> -->
