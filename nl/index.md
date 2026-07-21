---
layout: projects
title: Projecten
lang: nl
permalink: /nl/
---

<div class="posts projects">
  {% comment %}
    Eerst de projecten met een Nederlandse versie, daarna de nog niet vertaalde
    Engelse projecten — zo verdwijnt er niets van deze pagina zodra er één
    vertaling bijkomt. Vertalingen worden gekoppeld via `ref` in de front matter.
  {% endcomment %}
  {% assign nl_projects = site.categories.projects | where: "lang", "nl" %}
  {% assign translated_refs = nl_projects | map: "ref" | join: "," %}
  {% for project in nl_projects %}
    {% include project_card.html project=project more="Bekijk details" %}
  {% endfor %}
  {% for project in site.categories.projects %}
    {% if project.lang == "en" %}
      {% unless project.ref and translated_refs contains project.ref %}
        {% include project_card.html project=project more="Bekijk details" %}
      {% endunless %}
    {% endif %}
  {% endfor %}
</div>

## Neem contact op

[kenli@nyu.edu](mailto:kenli@nyu.edu)
