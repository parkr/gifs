---
title: "all dem gifs"
layout: default
---

## here be my collection of gifs, yo

{% assign topic = "" %}

{% for file in site.static_files %}{% capture new_topic %}{{ file.path | remove_first: '/' | split: '/' | first }}{% endcapture %}{% if new_topic != topic %}
- {{ new_topic }}{% assign topic = new_topic %}{% endif %}
  - [{{ file.path | split: '/' | last }}]({{ file.path }}){% endfor %}
