---
layout: default
title: High-Performance Computing - Matt Russell
permalink: /hpc/
---

{% for post in site.hpc %}
<div style="display:flex; justify-content:space-between; align-items:baseline;">
  <h4><a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h4>
  <p>{{ post.date | date_to_string }}</p>
</div>
{% endfor %}
