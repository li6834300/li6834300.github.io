---
layout: projects
title: Projecten
lang: nl
permalink: /nl/
---

<div class="posts projects">
  {% assign nl_projects = site.categories.projects | where: "lang", "nl" %}
  {% if nl_projects.size > 0 %}
    {% for project in nl_projects %}
      <article class="post">
        <div class="image {{project.align}}"><img src="{{ site.baseurl }}/images/{{project.preview}}"></div>
        <div class="entry">
          <h1><a href="{{ site.baseurl }}{{ project.url }}">
            <span class="tags">[{% for tag in project.tags %}{{tag.content}}{% if forloop.last == false %}, {% endif %}{% endfor %}]</span>
            {{ project.title }}</a></h1>
          {{ project.excerpt }}
        </div>
        {% for url in project.urlLinks %}
          <a href="{{ url.url }}" class="project-base-footer"> {{ url.name }}</a>
        {% endfor %}
        <a href="{{ site.baseurl }}{{ project.url }}" class="button button-primary">Lees meer</a>
      </article>
    {% endfor %}
  {% else %}
    {% for project in site.categories.projects %}
      <article class="post">
        <div class="image {{project.align}}"><img src="{{ site.baseurl }}/images/{{project.preview}}"></div>
        <div class="entry">
          <h1><a href="{{ site.baseurl }}{{ project.url }}">
            <span class="tags">[{% for tag in project.tags %}{{tag.content}}{% if forloop.last == false %}, {% endif %}{% endfor %}]</span>
            {{ project.title }}</a></h1>
          {{ project.excerpt }}
        </div>
        {% for url in project.urlLinks %}
          <a href="{{ url.url }}" class="project-base-footer"> {{ url.name }}</a>
        {% endfor %}
        <a href="{{ site.baseurl }}{{ project.url }}" class="button button-primary">Lees meer</a>
      </article>
    {% endfor %}
  {% endif %}
</div>

## Neem contact op

[kenli@nyu.edu](mailto:kenli@nyu.edu)
