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
    
    <li>{{ authors | join: ", " }}.
        {{ article["Year"]| slice: 0, 4 }}.
        <i>{{ article["Publication"] }}{{ article["Publisher"] }}</i>.      
    </li>

  {% endfor %}
{% endfor %}
</ul>
