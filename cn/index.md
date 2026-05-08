---
layout: projects
title: 项目
lang: cn
permalink: /cn/
---

<div class="posts projects">
  {% assign cn_projects = site.categories.projects | where: "lang", "cn" %}
  {% if cn_projects.size > 0 %}
    {% for project in cn_projects %}
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
        <a href="{{ site.baseurl }}{{ project.url }}" class="button button-primary">查看详情</a>
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
        <a href="{{ site.baseurl }}{{ project.url }}" class="button button-primary">查看详情</a>
      </article>
    {% endfor %}
  {% endif %}
</div>

## 联系我

[kenli@nyu.edu](mailto:kenli@nyu.edu)
