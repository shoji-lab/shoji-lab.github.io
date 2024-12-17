---
layout: page
title: Research
permalink: /research/
---

研究テーマの紹介

{% for item in site.researches %}
  <h2>{{ item.title }}</h2>
  <p>{{ item.description }}</p>
  <p><a href="{{ item.url }}">{{ item.title }}</a></p>
{% endfor %}

