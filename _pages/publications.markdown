---
layout: page
title: Publications
permalink: publications.html
---


<ul>
  {% assign sorted = site.data.hal | sort: "Year" | reverse %}
  {% assign article_by_year = sorted | group_by: "Year" %}
  
  {% for year in article_by_year %}
    <h2 style="margin-top: 40px;">{{ year.name }}</h2>
    {% for article in year.items %}
      {% assign authors = article["Authors"] | split: ";" %}
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
