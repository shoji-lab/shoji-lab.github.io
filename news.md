---
layout: page
title: News
permalink: /news/
description: "静岡大学情報学部行動情報学科で情報アクセス技術の研究を行っている「莊司慶行研究室」の、最近の活動内容や雑記の一覧です。"

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
  <!-- <div class="news-list">
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
/* ===== News cards (news page) ===== */
.lab-news-list{
  display: grid;
  grid-template-columns: 1fr;
  gap: 14px;
  margin: 0;
  padding: 0;
}

.lab-news-card{
  display: grid;
  grid-template-columns: 160px 1fr;  /* 左サムネ / 右本文 */
  gap: 14px;
  align-items: stretch;
  background: #fff;
  border: 1px solid #e9ecef;
  border-radius: 14px;
  padding: 14px;
  text-decoration: none;
  color: inherit;
  box-shadow: 0 2px 10px rgba(0,0,0,0.04);
  transition: transform .15s ease, box-shadow .15s ease, border-color .15s ease;
}

.lab-news-card:hover{
  transform: translateY(-2px);
  border-color: #dee2e6;
  box-shadow: 0 10px 22px rgba(0,0,0,0.08);
}

.lab-news-card--no-thumb{
  grid-template-columns: 1fr;
}

.lab-news-card__thumb{
  width: 100%;
  height: 100%;
}

.lab-news-card__thumb img{
  width: 100%;
  height: 100%;
  aspect-ratio: 16 / 10;
  object-fit: cover;
  border-radius: 10px;
  display: block;
}

.lab-news-card__body{
  min-width: 0; /* 省略表示のため */
}

.lab-news-card__meta{
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 8px;
  margin-bottom: 6px;
}

.lab-news-card__date{
  font-size: 0.85rem;
  color: #6c757d;
}

.lab-news-card__chips{
  display: inline-flex;
  flex-wrap: wrap;
  gap: 6px;
}

.lab-chip{
  display: inline-flex;
  align-items: center;
  border-radius: 999px;
  padding: 2px 8px;
  font-size: 0.78rem;
  line-height: 1.4;
  border: 1px solid #e9ecef;
  background: #f8f9fa;
  color: #495057;
  white-space: nowrap;
}

.lab-chip--category{
  background: #eef6ff;
  border-color: #d7eaff;
  color: #245a9a;
}

.lab-chip--tag{
  background: #f5f3ff;
  border-color: #e6ddff;
  color: #5034a3;
}

.lab-news-card__title{
  margin: 0 0 6px;
  font-size: 1.05rem;
  line-height: 1.35;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

.lab-news-card__excerpt{
  margin: 0;
  color: #495057;
  font-size: 0.95rem;
  line-height: 1.5;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

/* Responsive */
@media (max-width: 720px){
  .lab-news-card{
    grid-template-columns: 140px 1fr;
    padding: 12px;
  }
}

@media (max-width: 560px){
  .lab-news-card{
    grid-template-columns: 1fr;
  }
  .lab-news-card__thumb{
    order: -1;
  }
  .lab-news-card__thumb img{
    aspect-ratio: 16 / 9;
  }
}
</style>


<div class="lab-news-list">
  {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}

  {%- for post in site.posts -%}
    {%- assign thumb = post.thumbnail | default: post.image | default: post.thumb | default: "" -%}
    {%- if thumb == "" -%}
      {%- assign html = post.content | markdownify -%}
      {%- assign split_by_src = html | split: 'src="' -%}
      {%- if split_by_src.size > 1 -%}
        {%- assign after_src = split_by_src[1] -%}
        {%- assign thumb = after_src | split: '"' | first -%}
      {%- endif -%}
    {%- endif -%}
    {%- if thumb != "" and (thumb contains '://') == false -%}
      {%- assign thumb = thumb | relative_url -%}
    {%- endif -%}

    {%- assign card_classes = "lab-news-card" -%}
    {%- if thumb == "" -%}
      {%- assign card_classes = card_classes | append: " lab-news-card--no-thumb" -%}
    {%- endif -%}

    <a class="{{ card_classes }}" href="{{ post.url | relative_url }}">
      {%- if thumb != "" -%}
        <div class="lab-news-card__thumb">
          <img
            src="{{ thumb }}"
            alt=""
            loading="lazy"
            decoding="async"
            fetchpriority="low"
          >
        </div>
      {%- endif -%}

      <div class="lab-news-card__body">
        <div class="lab-news-card__meta">
          <span class="lab-news-card__date">{{ post.date | date: date_format }}</span>

          {%- comment -%} カテゴリ（複数可） {%- endcomment -%}
          {%- if post.categories and post.categories.size > 0 -%}
            <span class="lab-news-card__chips">
              {%- for c in post.categories -%}
                <span class="lab-chip lab-chip--category">{{ c }}</span>
              {%- endfor -%}
            </span>
          {%- endif -%}

          {%- comment -%} タグ（複数可） {%- endcomment -%}
          {%- if post.tags and post.tags.size > 0 -%}
            <span class="lab-news-card__chips">
              {%- for t in post.tags -%}
                <span class="lab-chip lab-chip--tag">#{{ t }}</span>
              {%- endfor -%}
            </span>
          {%- endif -%}
        </div>

        <h3 class="lab-news-card__title">{{ post.title | escape }}</h3>

        {%- if site.show_excerpts and post.excerpt -%}
          <p class="lab-news-card__excerpt">{{ post.excerpt | strip_html | truncate: 140 }}</p>
        {%- endif -%}
      </div>
    </a>
  {%- endfor -%}
</div>

<style>
/* カテゴリボタン */
.category-buttons {
  margin-bottom: 20px;
  display: flex;
  flex-wrap: wrap; 
  gap: 10px; 
  justify-content: center; 
}

.category-button {
  padding: 10px 20px;
  font-size: 14px;
  color: #007BFF;
  background-color: #f8f9fa;
  border: 1px solid #007BFF;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease, color 0.3s ease;
  flex: 1 1 auto; 
  text-align: center;
  max-width: 150px; 
}

.category-button.active, .category-button:hover {
  background-color: #007BFF;
  color: white;
}


@media (max-width: 600px) {
  .category-button {
    flex: 1 0 100%; /* ボタンを1列に配置 */
    max-width: none; /* 最大幅を解除 */
  }
}

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
  color: black;
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
