---
layout: default
title: Mathematics - Matt Russell
permalink: /math/
---

{% for post in site.math %}
<div style="display:flex; justify-content:space-between; align-items:baseline;">
  <h4><a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h4>
  <p>{{ post.date | date_to_string }}</p>
</div>
{% endfor %}
