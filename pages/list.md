---
layout: default
title: List
weight: 7
permalink: /list/
---
# **List of external URLs**

{% for post in site.lists reversed %}
  {% include lists/index.html %}
{% endfor %}
