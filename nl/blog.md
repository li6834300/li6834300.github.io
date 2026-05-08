---
layout: default
title: Blog
lang: nl
permalink: /nl/blog/
---

<div class="posts">
  {% assign nl_posts = site.categories.blog | where: "lang", "nl" %}
  {% for post in nl_posts %}
    <article class="post">
      <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>
      <div class="entry">
        {{ post.excerpt }}
      </div>
      <a href="{{ site.baseurl }}{{ post.url }}" class="button button-primary">Lees meer</a>
    </article>
  {% endfor %}
</div>
