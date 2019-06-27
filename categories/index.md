---
layout: page
title: Conference Index
excerpt: "An archive of posts sorted by conference."
search_omit: true
---

{% assign all_categories = site.categories %}
{% assign alphabetical_categories = (all_categories | sort_natural) %}
{% for category in alphabetical_categories %}
  <h3>{{ category }}</h3>
  <ul>
    {% for post in category %}
      <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}