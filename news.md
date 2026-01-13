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

<div class="view-toggle" role="group" aria-label="表示切替">
  <button type="button" class="view-button active" data-view="card" aria-pressed="true" aria-label="カード表示">
    <span class="view-icon view-icon--card" aria-hidden="true"></span>
  </button>
  <button type="button" class="view-button" data-view="list" aria-pressed="false" aria-label="リスト表示">
    <span class="view-icon view-icon--list" aria-hidden="true"></span>
  </button>
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

/* ===== view toggle (既にあるなら調整不要) ===== */
.news-controls{
  display:flex;
  gap:10px;
  align-items:center;
  justify-content:space-between;
  flex-wrap:wrap;
  margin-bottom:12px;
}
.view-toggle{
  display:inline-flex;
  border:1px solid #e9ecef;
  border-radius:10px;
  overflow:hidden;
  background:#fff;
}
.view-button{
  appearance:none;
  border:0;
  background:transparent;
  padding:8px 10px;
  font-size:0.9rem;
  cursor:pointer;
}
.view-button.active{
  background:#f1f3f5;
  font-weight:600;
}

/* ===== view toggle: right aligned + icon buttons ===== */

/* 右寄せ：inline-flex だと右寄せにできないので、要素自体を右寄せブロック扱いにする */
.view-toggle{
  display: inline-flex;
  margin-left: auto;          /* 効く条件が限られるので保険 */
  float: right;               /* 最短で右寄せにするならこれが確実 */
  margin-top: 6px;
  margin-bottom: 12px;
}

/* float を使うと後続要素が回り込むので解除（news list側の先頭で解除） */
.lab-news-list{
  clear: both;
}

/* ボタンをアイコン用に調整 */
.view-button{
  padding: 8px;               /* 文字がないので正方形寄りに */
  width: 40px;
  height: 40px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}

/* アイコン本体の枠 */
.view-icon{
  width: 20px;
  height: 20px;
  display: inline-block;
}

/* カード＝横棒4本（backgroundで描画） */
.view-icon--list{
  background:
    linear-gradient(#333 0 0) 0 0 / 100% 3px,
    linear-gradient(#333 0 0) 0 6px / 100% 3px,
    linear-gradient(#333 0 0) 0 12px / 100% 3px,
    linear-gradient(#333 0 0) 0 18px / 100% 3px;
  background-repeat: no-repeat;
  border-radius: 2px;
}

/* リスト＝四角が縦に3個（2個にしたいなら3行目を消す） */
.view-icon--card{
  position: relative;
  width: 20px;
  height: 20px;
  background:
    /* 1段目カード枠 */
    linear-gradient(#333 0 0) 0 0 / 20px 8px,
    /* 1段目サムネ */
    linear-gradient(#333 0 0) 2px 2px / 4px 4px,
    /* 1段目テキスト */
    linear-gradient(#333 0 0) 8px 3px / 10px 2px,

    /* 2段目カード枠 */
    linear-gradient(#333 0 0) 0 12px / 20px 8px,
    /* 2段目サムネ */
    linear-gradient(#333 0 0) 2px 14px / 4px 4px,
    /* 2段目テキスト */
    linear-gradient(#333 0 0) 8px 15px / 10px 2px;
  background-repeat: no-repeat;
  border-radius: 2px;
}

/* アクティブ時：既存の active 背景に加えてアイコンも少し強調したいなら */
.view-button.active .view-icon{
  filter: none;
}


/* ===== list view: no image, compact list ===== */
.news-view[data-view="list"] .lab-news-card{
  display:flex;                /* gridやめる */
  gap:10px;
  align-items:baseline;
  padding:10px 6px;
  border:0;
  border-radius:0;
  background:transparent;
  box-shadow:none;
  border-bottom:1px solid #eef1f4; /* 区切り線 */
  transform:none;
}

.news-view[data-view="list"] .lab-news-card:hover{
  transform:none;
  box-shadow:none;
  background:#fafbfc;          /* うっすらホバー */
}

/* 画像は完全に消す */
.news-view[data-view="list"] .lab-news-card__thumb{
  display:none !important;
}

/* メタ情報は1行でコンパクトに */
.news-view[data-view="list"] .lab-news-card__meta{
  margin:0;
  gap:8px;
}

/* 抜粋は消す（密度優先） */
.news-view[data-view="list"] .lab-news-card__excerpt{
  display:none !important;
}

/* タイトルは基本1行（必要なら2行に変えてOK） */
.news-view[data-view="list"] .lab-news-card__title{
  margin:0;
  font-size:0.98rem;
  line-height:1.35;
  display:-webkit-box;
  -webkit-line-clamp:1;
  -webkit-box-orient:vertical;
  overflow:hidden;
}

/* 日付は左に固定したいなら width を与える */
.news-view[data-view="list"] .lab-news-card__date{
  font-size:0.85rem;
  color:#6c757d;
  white-space:nowrap;
}

/* チップも少し小さく */
.news-view[data-view="list"] .lab-chip{
  font-size:0.74rem;
  padding:1px 7px;
}


</style>


<div class="lab-news-list news-view" data-view="card">
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

{%- capture cats -%}
  {%- for c in post.categories -%}
    {{ c | downcase }}{% unless forloop.last %} {% endunless %}
  {%- endfor -%}
{%- endcapture -%}

{%- capture tags -%}
  {%- for t in post.tags -%}
    {{ t | downcase }}{% unless forloop.last %} {% endunless %}
  {%- endfor -%}
{%- endcapture -%}

    <!-- <a class="{{ card_classes }} news-item" href="{{ post.url | relative_url }}" data-category="{{ cats | downcase }}" data-tags="{{ tags | downcase }}" > -->
    <a class="{{ card_classes }} news-item"    href="{{ post.url | relative_url }}"    data-category="{{ cats | strip }}"    data-tags="{{ tags | strip }}">
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
document.addEventListener("DOMContentLoaded", () => {
  // ---------- Category filter ----------
  (() => {
    const buttons = Array.from(document.querySelectorAll(".category-button"));
    const items   = Array.from(document.querySelectorAll(".news-item"));
    if (buttons.length === 0 || items.length === 0) return;

    function applyCategory(category) {
      buttons.forEach(btn => {
        const on = (btn.getAttribute("data-category") || "all") === category;
        btn.classList.toggle("active", on);
        btn.setAttribute("aria-pressed", on ? "true" : "false");
      });

      items.forEach(item => {
        const raw = (item.getAttribute("data-category") || "");
        const tokens = raw.split(/\s+/).filter(Boolean); // data-category はスペース区切り前提
        const show = (category === "all") || tokens.includes(category);
        item.hidden = !show; // displayをいじらない
      });
    }

    buttons.forEach(btn => {
      btn.addEventListener("click", () => {
        const category = (btn.getAttribute("data-category") || "all").trim();
        applyCategory(category);
      });
    });

    applyCategory("all");
  })();

  // ---------- View toggle (card/list) ----------
  (() => {
    const viewRoot = document.querySelector(".news-view");
    const viewButtons = Array.from(document.querySelectorAll(".view-button"));
    if (!viewRoot || viewButtons.length === 0) return;

    const storageKey = "newsViewMode";

    function setView(mode) {
      viewRoot.setAttribute("data-view", mode);
      viewButtons.forEach(btn => {
        const on = (btn.getAttribute("data-view") === mode);
        btn.classList.toggle("active", on);
        btn.setAttribute("aria-pressed", on ? "true" : "false");
      });
      try { localStorage.setItem(storageKey, mode); } catch (e) {}
    }

    let initial = "card";
    try {
      const saved = localStorage.getItem(storageKey);
      if (saved === "card" || saved === "list") initial = saved;
    } catch (e) {}

    // 初回スマホはリストに倒したいなら（保存が無い場合だけ）
    if (initial === "card" && window.matchMedia("(max-width: 560px)").matches) {
      // savedが無かった場合だけにしたいなら、上の saved 判定にフラグを足してください
      initial = "list";
    }

    viewButtons.forEach(btn => {
      btn.addEventListener("click", () => setView(btn.getAttribute("data-view")));
    });

    setView(initial);
  })();
});
</script>

