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
div.title{
font-size:600%;
font-weight:bolder;
}

div.subsitle{
font-size:400%;
font-weight:bold;
}

span.caution{
color:red;
font-weight:bold;
}

.carousel {
  position: relative; /* 子要素を絶対配置するために必要 */
  width: 100%;
  height: 20%;
  display: flex;
  overflow: hidden;
  margin: 0 auto;
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
  white-space: pre-wrap; /* 改行と複数スペースを許可 */
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
  20% { margin-left: -100%; }
  /* 少しの間上と同じ位置 */  
  25% { margin-left: -100%; }
  /* 2個分左の位置に進めて3個目の画像を左端にする */
  45% { margin-left: -200%; }
  /* 少しの間上と同じ位置 */  
  50% { margin-left: -200%; }
  /* 以降は上と同様に繰り返し */
  70% { margin-left: -300%; }
  75% { margin-left: -300%; }
  95% { margin-left: -400%; }
  100% { margin-left: -400%; }
}
/* カルーセルの子要素にスクロールアニメーションを設定 */
.carousel > :first-child {
  animation-name: scroll;    /* キーフレーム名 */
  animation-duration: 20s;  /* 再生時間全体は20秒 */
  animation-delay: 0s;      /* 読込直後から遅延無しで開始 */
  animation-iteration-count: infinite;  /* 無限に繰り返す */
}

.carousel img {
  margin: 0;
  padding: 0;
  display: block; /* imgタグの改行のすき間を消すため */
  filter: brightness(50%); /* 明るさを50%に調整 */
}

</style>

<!-- カルーセルの外枠 -->
<div class="carousel">
  <img src="./assets/img/index/top1.jpg">
  <img src="./assets/img/index/top2.jpg">
  <img src="./assets/img/index/top4.jpg">
  <img src="./assets/img/index/top5.jpg">  
  <img src="./assets/img/index/top1.jpg">
  <div class="text-overlay">
    <div class="sustitle">静岡大学 情報学部 行動情報学科</div>
    <div class="title">莊司研究室</div>
  </div>
</div>


莊司研究室では「人と社会を考慮した情報アクセス技術」の研究室として、
情報検索アプリケーションやWeb情報学、ソーシャルコンピューティングなどの研究を行っています。

研究室の概要、配属希望者向けの情報は[こちら](./about)。

研究プロジェクト、研究テーマは[こちら](./research)。


<h2>最新情報</h2>

<!-- ![写真](/assets/img/index/index.jpg "研究室") -->