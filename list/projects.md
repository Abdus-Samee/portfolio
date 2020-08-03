---
title: Projects
narrow: true
permalink: list/projects.html
show_profile: true
---

{% for project in site.projects %}
  <div class = "card mb-2">
    <div class = "card-body">
      <h3 class = "card-title"><a href = "{{ site.baseurl }}{{ project.url }}">{{ project.title }}</a></h3>
      <div class="card-text mb-0">
          {{ project.excerpt }}
      </div>
      <a class = "card-subtitle mb-2" href="{{ project.url | absolute_url }}">More...</a>
    </div>
  </div>
{% endfor %}
