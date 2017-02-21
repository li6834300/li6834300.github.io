---
layout: projects
title: Projects
---

<div class="posts projects">
  {% for project in site.categories.projects %}
    <article class="post">


    <div class="image"><img src="{{ site.baseurl }}/images/{{project.preview}}"></div>
      <div class="entry">
      <h1><a href="{{ site.baseurl }}{{ project.url }}">{{ project.title }}</a></h1>
        {{ project.excerpt }}


      </div>



      <a href="{{ site.baseurl }}{{ project.url }}" class="button button-primary">Read More</a>
    </article>
  {% endfor %}
</div>


## Contact me

[kenli@nyu.edu](mailto:kenli@nyu.edu)
