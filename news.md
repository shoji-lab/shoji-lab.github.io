---
layout: page
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
  display: block; /* 日付をタイトルの上に表示 */
  font-size: 14px; /* 日付を小さめのフォントサイズに設定 */
  color: #666; /* 日付を灰色に設定 */
  margin-bottom: 5px; /* タイトルとの間に余白を追加 */
}

.news-title {
  font-size: 16px; /* タイトルを少し大きめに設定 */
  font-weight: bold; /* タイトルを太字に設定 */
  color: #007BFF; /* タイトルリンクを青色に設定 */
  text-decoration: none; /* 下線を削除 */
}

.news-title:hover {
  text-decoration: underline; /* ホバー時に下線を表示 */
}


</style>