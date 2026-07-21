---
layout: projects
title: 项目
lang: cn
permalink: /cn/
---

<div class="posts projects">
  {% comment %}
    先列出有中文版的项目，再补上尚未翻译的英文项目——
    这样新增一个中文版不会把其它项目从中文页面挤掉。
    英文版与中文版通过 front matter 里的 ref 配对。
  {% endcomment %}
  {% assign cn_projects = site.categories.projects | where: "lang", "cn" %}
  {% assign translated_refs = cn_projects | map: "ref" | join: "," %}
  {% for project in cn_projects %}
    {% include project_card.html project=project more="查看详情" %}
  {% endfor %}
  {% for project in site.categories.projects %}
    {% if project.lang == "en" %}
      {% unless project.ref and translated_refs contains project.ref %}
        {% include project_card.html project=project more="查看详情" %}
      {% endunless %}
    {% endif %}
  {% endfor %}
</div>

## 联系我

[kenli@nyu.edu](mailto:kenli@nyu.edu)
