---
layout: archive
title: "Conferences Contributions"
permalink: /conferences/
author_profile: true
---

{% include base_path %}

{% for post in site.conferences reversed %}
  {% include archive-single.html %}
{% endfor %}
