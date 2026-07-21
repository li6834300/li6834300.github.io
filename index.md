---
layout: projects
title: Projects
---

<div class="posts projects">
  {% comment %} Only English projects here; /cn and /nl list their own. {% endcomment %}
  {% assign projects = site.categories.projects | where: "lang", "en" %}
  {% for project in projects %}
    {% include project_card.html project=project more="Read More" %}
  {% endfor %}
</div>


## Contact me

[kenli@nyu.edu](mailto:kenli@nyu.edu)
