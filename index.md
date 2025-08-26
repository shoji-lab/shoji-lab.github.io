---
#
# By default, content added below the "---" mark will appear in the home page
# between the top bar and the list of recent posts.
# To change the home page layout, edit the _layouts/home.html file.
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
#
layout: home
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
    font-size:150%;
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
/*↑ 莊司追加分******************************************************/


</style>

<div class="carousel">
  <img src="./assets/img/index/top1.jpg">
  <img src="./assets/img/index/top2.jpg">
  <img src="./assets/img/index/top4.jpg">
  <img src="./assets/img/index/top5.jpg">  
  <img src="./assets/img/index/top3.png">
  <!-- リセット時にかくつかないようにするために最初の要素を追加 -->
  <img src="./assets/img/index/top1.jpg">
  <!-- 枚数、5枚用にしてあるので、新しい画像を入れたら1枚コメントアウトする-->
  <div class="text-overlay">
    <div class="subtitle">静岡大学 情報学部 行動情報学科</div>
    <div class="title">莊司研究室</div>
  </div>
</div>

静岡大学 情報学部 行動情報学科 / 静岡大学大学院 総合科学技術研究科 情報学専攻 莊司慶行研究室では「人と社会を考慮した情報アクセス技術」の研究室として、
情報検索アプリケーションやWeb情報学、ソーシャルコンピューティングなどの研究を行っています。
人々が必要な時に必要な情報を獲得できるようにするために、ウェブ技術、データベース技術、機械学習（AI）技術などを活用して、さまざまな研究を進めています。

<div class="navigation">
<ul>
<li>研究室の概要、配属希望者向けの情報は<a href="./about">こちら</a>。</li>
<li>研究プロジェクト、研究テーマは<a href="./research">こちら</a>。</li>
<li>Please check our <a href="./about">research and application details</a> before contacting us.</li>
</ul>
</div>


<hr>
<h2>最新情報</h2>

<!-- ![写真](/assets/img/index/index.jpg "研究室") -->