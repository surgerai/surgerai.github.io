---
layout: page
title: Publications
permalink: publications.html
---

<ul>
{% assign article_by_year = site.data.hal | group_by: "Year" %}
{% for year in article_by_year %}
  <h2>{{ year.name }}</h2>
  {% for article in year.items %}
    {% assign authors = article["Authors"] | split: ";" %}
    {% assign title = article["Title"] %}
    
    <li>
        {{ title }}.
        {{ authors | join: ", " }}.
        <i>{{ article["Publication"] }}</i>.
        {% if article["Volume"] %}{{ article["Volume"] }}, {% endif %}
        {% if article["Number"] %}{{ article["Number"] }}, {% endif %}
        {% if article["Pages"] %}{{ article["Pages"] }}, {% endif %}
        {% if article["Publisher"] %}{{ article["Publisher"] }}, {% endif %}
    </li>

  {% endfor %}
{% endfor %}
</ul>
