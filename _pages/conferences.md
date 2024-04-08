---
layout: archive
title: "Conferences Contributions"
permalink: /conferences/
author_profile: true
---

{% include base_path %}

{% assign years = "" | split: "" %}

{% for post in site.conferences %}
  {% capture conference_year %}{{ post.date | date: "%Y" }}{% endcapture %}
  {% unless years contains conference_year %}
    {% assign years = years | push: conference_year %}
  {% endunless %}
{% endfor %}

{% assign sorted_years = years | sort | reverse %}

{% for year in sorted_years %}
  <h2>{{ year }}</h2>
  {% for post in site.conferences %}
    {% capture post_year %}{{ post.date | date: "%Y" }}{% endcapture %}
    {% if post_year == year %}
      {% include archive-single.html %}
    {% endif %}
  {% endfor %}
{% endfor %}
