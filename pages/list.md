---
layout: default
title: List
weight: 7
permalink: /list/
---
# **Links & Resources**

{% for post in site.posts reversed %}
  {% include archive-single.html %}
{% endfor %}
