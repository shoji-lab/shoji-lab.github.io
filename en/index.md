---
layout: home
permalink: /en/
---

<style>
div.title {
  font-size: clamp(2rem, 15vw, 600%); /* 最小2rem、最大600% */
  font-weight: bolder;
  text-align: center; /* 中央揃え */
  line-height: 1.2; /* 行間を調整 */
}

div.subtitle {
  font-size: clamp(1rem, 5vw, 200%); /* 最小1rem、最大200% */
  font-weight: bold;
  text-align: center; /* 中央揃え */
  line-height: 1.5; /* 行間を調整 */
}

span.caution{
color:red;
font-weight:bold;
}

div.navigation{
    font-size:120%;
}

.carousel {
  position: relative; /* 子要素を絶対配置するために必要 */
  width: 100%;
  height: 20%;
  display: flex;
  overflow: hidden;
  margin: 0 auto;
  z-index: 0;
}

/* テキストオーバーレイ */
.text-overlay {
  position: absolute; /* ラッパー内で固定配置 */
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column; /* テキストを縦方向に並べる */
  justify-content: center; /* 垂直方向の中央揃え */
  align-items: center; /* 水平方向の中央揃え */
  z-index: 2; /* カルーセルの上に配置 */
  pointer-events: none; /* ユーザー操作を無効化 */
  white-space: nowrap; /* 改行と複数スペースを許可 */
  text-align: center; /* 中央揃え（オプション） */
  color: white; /* 文字色 */
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7); /* ドロップシャドウ */
}


/* カルーセル内の画像 */
.carousel img {
  margin: 0;
  padding: 0;
  display: block; /* imgタグの改行のすき間を消すため */
}
/* スクロールアニメーションのキーフレーム */
@keyframes scroll {
  /* 初期位置は1個目の画像が左端 */
  0% { margin-left: 0; }      
  /* 1個分左の位置に進めて2個目の画像を左端にする */
  15% { margin-left: -100%; }
  /* 少しの間上と同じ位置 */  
  20% { margin-left: -100%; }
  /* 2個分左の位置に進めて3個目の画像を左端にする */
  35% { margin-left: -200%; }
  /* 少しの間上と同じ位置 */  
  40% { margin-left: -200%; }
  /* 以降は上と同様に繰り返し */
  55% { margin-left: -300%; }
  60% { margin-left: -300%; }
  75% { margin-left: -400%; }
  80% { margin-left: -400%; }
  95% { margin-left: -500%; }
  100% { margin-left: -500%; }
}
/* カルーセルの子要素にスクロールアニメーションを設定 */
.carousel > :first-child {
  animation-name: scroll;    /* キーフレーム名 */
  animation-duration: 25s;  /* 再生時間全体は20秒 */
  animation-delay: 0s;      /* 読込直後から遅延無しで開始 */
  animation-iteration-count: infinite;  /* 無限に繰り返す */
}

.carousel img {
  margin: 0;
  padding: 0;
  display: block; /* imgタグの改行のすき間を消すため */
  filter: brightness(50%); /* 明るさを50%に調整 */
}


/*↓ 莊司追加分******************************************************/
/* グリッド全体 */
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); 
  gap: 20px;
  max-width: 1000px;
  margin: 0 auto;
  padding: 20px;
}

/* カード */
.card {
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.1);
  overflow: hidden;
  text-align: center;
  transition: transform 0.2s ease;
}
.card:hover {
  transform: translateY(-5px);
}

/* 画像 */
.card img {
  width: 100%;
  height: 150px;
  object-fit: cover; /* 画像を枠にフィット */
}

/* タイトル */
.card h3 {
  font-size: 1rem;
  margin: 10px 0;
  padding: 0 10px;
  color: #333;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

/* ===== News cards ===== */
.lab-news-list {
  list-style: none;
  margin: 0;
  padding: 0;
  display: grid;
  gap: 16px;
}

/* カード全体をリンク化 */
.lab-news-card {
  display: grid;
  grid-template-columns: 1fr 140px; /* 本文 / サムネ */
  gap: 12px;
  align-items: center;
  background: #fff;
  border: 1px solid #e9ecef;
  border-radius: 12px;
  padding: 16px;
  text-decoration: none;
  color: inherit;
  box-shadow: 0 2px 8px rgba(0,0,0,0.04);
  transition: transform 0.15s ease, box-shadow 0.15s ease, border-color 0.15s ease;
}
.lab-news-card:hover {
  transform: translateY(-2px);
  border-color: #dee2e6;
  box-shadow: 0 6px 16px rgba(0,0,0,0.08);
}

/* サムネ無しなら1カラム */
.lab-news-card--no-thumb {
  grid-template-columns: 1fr;
}

/* 本文領域 */
.lab-news-card__date {
  display: inline-block;
  font-size: 0.85rem;
  color: #6c757d;
  margin-bottom: 6px;
}
.lab-news-card__title {
  margin: 0 0 6px;
  font-size: 1.05rem;
  line-height: 1.35;
  display: -webkit-box;              /* タイトル複数行省略（2行） */
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
.lab-news-card__excerpt {
  margin: 0;
  color: #495057;
  font-size: 0.95rem;
  line-height: 1.45;
}


.lab-news-card__thumb{
  width: 160px;
  height: 160px;         /* 好みで 120〜180 */
}

.lab-news-card__thumb img{
  width: 100%;
  height: 100%;
  object-fit: contain;
  background: #fff;
}
/* レスポンシブ */
@media (max-width: 720px) {
  .lab-news-card {
    grid-template-columns: 1fr 120px;
    padding: 14px;
  }
}
@media (max-width: 560px) {
  .lab-news-card {
    grid-template-columns: 1fr; /* 縦積み */
  }
  .lab-news-card__thumb {
    order: -1;          /* 画像を上に */
    margin-bottom: 8px;
  }
}

.lab-news-more {
  text-align: right;
  margin-top: 8px;
}

.lab-news-more a {
  color: #0077cc;         /* サイトのテーマカラーに合わせて調整 */
  font-weight: 500;
  text-decoration: none;
  transition: color 0.2s ease;
}

.lab-news-more a:hover {
  color: #005999;
  text-decoration: underline;
}

/*↑ 莊司追加分******************************************************/


</style>

<div class="carousel">
  <img src="/assets/img/index/top1.webp">
  <img src="/assets/img/index/top2.webp">
  <img src="/assets/img/index/top4.webp">
  <img src="/assets/img/index/top5.webp">  
  <img src="/assets/img/index/top3.webp">
  <img src="/assets/img/index/top1.webp">

  <div class="text-overlay">
    <div class="subtitle">
      Faculty of Informatics, Shizuoka University<br>
      Department of Behavioral Informatics
    </div>
    <div class="title">Shoji Laboratory</div>
  </div>
</div>

The Shoji Laboratory, affiliated with the <strong>Faculty of Informatics, Department of Behavioral Informatics, Shizuoka University</strong>, and the <strong>Graduate School of Integrated Science and Technology, Program in Informatics</strong>, conducts research on <strong>information access technologies that take human and societal factors into account</strong>.

Our research covers areas such as information retrieval applications, web informatics, and social computing. To enable people to obtain the information they need at the right time, we actively leverage web technologies, database technologies, and machine learning (AI), and pursue a wide range of research topics in information access.

<div class="navigation">
<ul>
  <li>
    An overview of the laboratory and information for prospective students is available
    <a href="/en/about">here</a>.
  </li>
  <li>
    Our research projects and research topics can be found
    <a href="/en/research">here</a>.
  </li>
  <li>
    Please review our <a href="/en/about">research scope and application details</a>
    before contacting us.
  </li>
</ul>
</div>

<!-- ![Photo](/assets/img/index/index.jpg "Laboratory") -->

<!-- ![写真](/assets/img/index/index.jpg "研究室") -->
