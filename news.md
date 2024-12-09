---
layout: page
title: News
permalink: /news/
---

莊司研究室の活動を掲載しています！

<div class="news-container">
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
</div>

<style>
/* カテゴリボタン */
<style>
/* カテゴリボタンの親コンテナ */
.category-buttons {
  margin-bottom: 20px;
  display: flex;
  flex-wrap: wrap; /* ボタンが画面幅を超えたら折り返し */
  gap: 10px; /* ボタン間の隙間 */
  justify-content: center; /* ボタンを中央揃え */
}

/* カテゴリボタン */
.category-button {
  padding: 10px 20px;
  font-size: 14px;
  color: #007BFF;
  background-color: #f8f9fa;
  border: 1px solid #007BFF;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease, color 0.3s ease;
  flex: 1 1 auto; /* ボタンを同じサイズに広げる */
  text-align: center;
  max-width: 150px; /* ボタンの最大幅 */
}

.category-button.active, .category-button:hover {
  background-color: #007BFF;
  color: white;
}

/* スマートフォン対応（画面幅600px以下） */
@media (max-width: 600px) {
  .category-button {
    flex: 1 0 100%; /* ボタンを1列に配置 */
    max-width: none; /* 最大幅を解除 */
  }
}
</style>


/* ニュースリスト */
.news-list ul {
  list-style: none;
  padding: 0;
}

.news-item {
  margin-bottom: 15px;
}

.news-date {
  display: block;
  font-size: 14px;
  color: #666;
}

.news-title {
  font-size: 16px;
  font-weight: bold;
  color: #007BFF;
  text-decoration: none;
}

.news-title:hover {
  text-decoration: underline;
}

</style>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    const buttons = document.querySelectorAll(".category-button");
    const items = document.querySelectorAll(".news-item");

    buttons.forEach((button) => {
      button.addEventListener("click", () => {
        const category = button.getAttribute("data-category");

        // ボタンのアクティブ状態を更新
        buttons.forEach((btn) => btn.classList.remove("active"));
        button.classList.add("active");

        // カテゴリに応じて表示・非表示を切り替え
        items.forEach((item) => {
          if (category === "all" || item.getAttribute("data-category").includes(category)) {
            item.style.display = "block";
          } else {
            item.style.display = "none";
          }
        });
      });
    });
  });
</script>
