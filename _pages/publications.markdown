---
layout: page
title: Publications
permalink: publications.html
---

<ul>
{% assign article_by_year = site.data.hal | group_by: "Year" | reverse %}
{% for year in article_by_year %}
  <h2>{{ year.name }}</h2>
  {% for article in year.items %}
    {% assign authors = article["Authors"] | split: ";" %}
    {% assign authors = authors | map: "strip" %}
    {% assign title = article["Title"] %}
    
    <li>
        {{ title }}.
        {{ authors | join: ", " }}.
        <i>{{ article["Publication"] }}</i>.
        {% if article["Publisher"] %}{{ article["Publisher"] }}. {% endif %}
    </li>

  {% endfor %}
{% endfor %}
</ul>
