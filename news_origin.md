---
layout: page
title: Newss
permalink: /news_origin/
---

莊司研究室の活動を掲載しています！

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

<!-- <div class="news-container">
  <!-- カテゴリ選択ボタン -->
  <div class="category-buttons">
    <button class="category-button" data-category="all">すべて</button>
    <button class="category-button" data-category="論文">論文</button>
    <button class="category-button" data-category="研究室">研究室</button>
    <button class="category-button" data-category="発表">発表</button>
    <button class="category-button" data-category="雑談">雑談</button>
  </div>

  <!-- ニュース一覧 -->
  <div class="news-list">
    <ul>
      {% for post in site.posts %}
        <li class="news-item" data-category="{{ post.categories }}">
          <span class="news-date">{{ post.date | date: "%b %-d, %Y" }}</span>
          <a href="{{ post.url | relative_url }}" class="news-title">{{ post.title }}</a>
        </li>
      {% endfor %}
    </ul>
  </div>
</div> -->

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