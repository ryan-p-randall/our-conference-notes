---
layout: page
title: Conference Index
excerpt: "An archive of posts sorted by conference."
search_omit: true
---

{% assign all_categories = site.categories %}
{% assign alphabetical_categories = (all_categories | sort_natural) %}
{% for item in alphabetical_categories %}
  <h3>{{ item[0] }}</h3>
  <ul>
    {% for post in item[1] %}
      <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}