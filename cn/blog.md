---
layout: default
title: 博客
lang: cn
permalink: /cn/blog/
---

<div class="posts">
  {% assign cn_posts = site.categories.blog | where: "lang", "cn" %}
  {% for post in cn_posts %}
    <article class="post">
      <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>
      <div class="entry">
        {{ post.excerpt }}
      </div>
      <a href="{{ site.baseurl }}{{ post.url }}" class="button button-primary">阅读全文</a>
    </article>
  {% endfor %}
</div>
