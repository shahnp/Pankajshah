---
layout: posts
permalink: /Project/
title: "Projects Posts by Tags"
author_profile: true
header:
  image: "/images/zakim_bridge.png"
---

{% include base_path %}
{% include group-by-array
collection=site.posts field = "tags" %}

{% for tag in group_names %}
  {% assign posts =
  group_itmes[forloop.index0] %}
  <h2 id ="{{tag | slugify }}"
  class ="archive_subtitle">{{ tag }}</h2>
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}
