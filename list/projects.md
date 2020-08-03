---
title: Projects
narrow: true
permalink: list/projects.html
show_profile: true
---

{% for project in site.projects %}
  <h3><a href = "{{ site.baseurl }}{{ project.url }}">{{ project.title }}</a></h3>
  <div class="card-text mb-0">
      {{ project.excerpt }}
  </div>
  <a href="{{ project.url | absolute_url }}">More...</a>
{% endfor %}
