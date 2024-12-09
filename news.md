---
layout: page
title: News
permalink: /news/
---

<div class="post-list">
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


<!-- <style>
.news-list {
  padding: 20px;
}

.news-list ul {
  list-style: none;
  padding: 0;
}

.news-list li {
  margin-bottom: 10px;
}

.news-date {
  font-weight: bold;
  margin-right: 10px;
}

.news-title {
  text-decoration: none;
  color: #007BFF;
}

.news-title:hover {
  text-decoration: underline;
}

</style> -->