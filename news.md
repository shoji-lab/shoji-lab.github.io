---
layout: base
title: News
permalink: /news/
---

<div class="news-list">
  {% assign posts = site.posts %}
  <ul>
    {% for post in posts %}
      <li>
        <span class="news-date">{{ post.date | date: "%b %-d, %Y" }}</span>
        <a href="{{ post.url | relative_url }}" class="news-title">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>
</div>


