---
layout: page
title: Conference Index
excerpt: "An archive of posts sorted by conference."
search_omit: true
---
{% assign alphabetical_categories = site.categories | sort %}
{% for category in alphabetical_categories %}
  {% assign sorted_posts = category[1] | reversed %}
  <h3>{{ category[0] }}</h3>
  <ul>
    {% for post in sorted_posts %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>  
{% endfor %}
{% comment %} Alphabetical logic from https://gist.github.com/Phlow/57eb457898e4ac4c4a20 , can't remember where <li> logic came from or if I made it {% endcomment %}