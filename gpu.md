---
layout: default
title: GPU
permalink: /gpu/
---

{% assign reversed_posts = site.gpu | reverse %}
{% for post in reversed_posts %}
<div style="display:flex; justify-content:space-between; align-items:baseline;">
  <h4><a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h4>
  <p>{{ post.date | date_to_string }}</p>
</div>
{% endfor %}
