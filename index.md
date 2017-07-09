---
layout: projects
title: Projects
---

<div class="posts projects">
  {% for project in site.categories.projects %}
    <article class="post">


    <div class="image {{project.align}}"><img src="{{ site.baseurl }}/images/{{project.preview}}"></div>
      <div class="entry">
      <h1><a href="{{ site.baseurl }}{{ project.url }}"> <span class="tags">[{% for tag in project.tags %}{{tag.content}}{% endfor %}]</span>
      {{ project.title }}</a></h1>
        {{ project.excerpt }}


      </div>

      {% for url in project.urlLinks %}
        <a href="{{ url.url }}" class="project-base-footer"> {{ url.name }}</a>
      {% endfor %}

      <a href="{{ site.baseurl }}{{ project.url }}" class="button button-primary">Read More</a>
    </article>
  {% endfor %}
</div>


## Contact me

[kenli@nyu.edu](mailto:kenli@nyu.edu)
