---
layout: page
title: Conference Index
excerpt: "An archive of posts sorted by conference."
search_omit: true
---

{% for category in site.categories %}
  <h3>{{ category[0] }}</h3>
  <ul>
    {% for post in category[1] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}



{%- capture site_categories -%}
    {%- for category in site.categories -%}
        {{- category | first -}}{%- unless forloop.last -%},{%- endunless -%}
    {%- endfor -%}
{%- endcapture -%}
{%- assign categories_list = site_categories | split:',' | sort -%}

{%- for category in categories_list -%}
    <a href="#{{- category -}}" class="btn btn-primary tag-btn"><i class="fa fa-tag" aria-hidden="true"></i>&nbsp;{{- category -}}&nbsp;({{site.categories[tag].size}})</a>
{%- endfor -%}

<div id="full-categories-list">
{%- for category in categories_list -%}
    <h2 id="{{- category -}}" class="linked-section">
        <i class="fa fa-tag" aria-hidden="true"></i>
        &nbsp;{{- category -}}&nbsp;({{site.categories[category].size}})
    </h2>
    <div class="post-list">
        {%- for post in site.categories[category] -%}
            <div class="category-entry">
                <a href="{{- site.url -}}{{- post.url -}}">{{- post.title -}}</a>
                <div class="entry-date">
                    <time datetime="{{- post.date | date_to_xmlschema -}}">{{- post.date | date: "%B %d, %Y" -}}</time>
                </div>
            </div>
        {%- endfor -%}
    </div>
{%- endfor -%}
</div>