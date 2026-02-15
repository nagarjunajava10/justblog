---
layout: default
title: Blog Posts
nav_order: 99
---

# Blog Posts

{% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}

{% for year in posts_by_year %}

## {{ year.name }}

  {% assign posts_by_month = year.items | group_by_exp: "post", "post.date | date: '%B'" %}

  {% for month in posts_by_month %}

  ### {{ month.name }}

  {% for post in month.items %}

  - [{{ post.title }}]({{ post.url | relative_url}}) ({{ post.date | date: "%b %d" }})

  {% endfor %}

  {% endfor %}

{% endfor %}
