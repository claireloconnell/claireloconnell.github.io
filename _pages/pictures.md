---
layout: archive
title: "Pictures"
permalink: /pictures/
author_profile: true
---

{% include base_path %}

{% for picture in site.pictures %}
  {% include archive-single.html %}
{% endfor %}
