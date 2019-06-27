---
layout: page
title: Conference Index
excerpt: "An archive of posts sorted by conference."
search_omit: true
---

{% assign alphabetical_categories = site.categories | sort_natural %}
{% for category in alphabetical_categories %}
  {% capture category_name %}{{ category | first }}{% endcapture %}
  <h3 class="category-head">{{ category_name }}</h3>
    {% for post in site.categories[category_name] %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  {% comment %}
  <h3>{{ category[0] }}</h3>
  <ul>
    {% for post in category[1] %}
      <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
  {% endcomment %}
{% endfor %}