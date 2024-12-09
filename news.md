---
layout: page
title: News
permalink: /news/
---

莊司研究室の活動を掲載しています！

<!-- <div class="news-list">
  {% assign posts = site.posts %}
  <ul>
    {% for post in posts %}
      <li>
        <span class="news-date">{{ post.date | date: "%b %-d, %Y" }}</span>
        <a href="{{ post.url | relative_url }}" class="news-title">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>
</div> -->

<div class="news-list">
  {% assign categories = site.posts | map: "categories" | uniq %}
  {% for category in categories %}
    <h2>{{ category }}</h2>
    {% assign category_posts = site.posts | where: "categories", category %}
    <ul>
      {% for post in category_posts %}
        <li>
          <span class="news-date">{{ post.date | date: "%Y年%-m月%-d日" }}</span>
          <a href="{{ post.url | relative_url }}" class="news-title">{{ post.title }}</a>
        </li>
      {% endfor %}
    </ul>
  {% endfor %}
</div>

<style>
.news-list {
  padding: 20px;
}

.news-list ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.news-list li {
  margin-bottom: 15px;
}

.news-date {
  display: block; 
  font-size: 14px; 
  color: #666; 
  margin-bottom: 5px;
}

.news-title {
  font-size: 20px; 
  font-weight: bold;
  color: #007BFF; 
  text-decoration: none;
}

.news-title:hover {
  text-decoration: underline; 
}


</style>