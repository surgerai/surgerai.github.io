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
    {% assign authors_raw = article["Authors"] %}
    {{ authors_raw }} <!-- Debug output: show the raw data -->
    {% assign authors = authors_raw | split: ";" %}
    {{ authors }} <!-- Debug output: show the authors after split -->

    
    
    <li>
        {{ title }}.
        {{ authors | join: ", " }}.
        <i>{{ article["Publication"] }}</i>.
        {% if article["Publisher"] %}{{ article["Publisher"] }}. {% endif %}
    </li>

  {% endfor %}
{% endfor %}
</ul>
