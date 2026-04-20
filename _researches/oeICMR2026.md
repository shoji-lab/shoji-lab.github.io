---
layout: research
title: "「○○な時に着るべき服装」を、画像認識AIと画像生成AIに推薦してもらおう！"
description: "ICMR2026「Asymmetric Pipeline for Dataset Construction and Situation-Aware Generative Outfit Retrieval Leveraging Differences in Task Difficulty」"
date: 20260420
thumbnail: "/assets/img/researches/oeICMR2026/thumb.png"
title_en: "Situation-aware Outfit Recommendation with Vision AI and Image Generation AI"
---

<div class="catch">
このシチュエーションでは何を着るべき？画像認識・生成AIに聞いてみよう
</div>
この研究では、「子供の運動会の付き添い」や「キャンパス生活」、「高級旅館に泊まるとき」などの特定のシチュエーションを入力すると、そこに適した服装を提案する検索・推薦システムについて提案しています。
このようなシステムを実現するために、多くの画像について「この画像は、何をしている場面？」と、画像認識AIに聞いて、画像とシチュエーション名のペアを作りました。
そして、画像生成AIをそのデータでトレーニングして、「こういうシチュエーションで、着られがちな服装」の画像を生成できるようにしました。

<div class="header">研究背景</div>
人々は、毎日、家を出る際には、必ず服を選んでいます。
とくに、何かイベントに参加する際には、服選びも大変です。
たとえば、「姪っ子のお誕生日会に参加する」といった際には、どんな服装が最適でしょうか？
ほかにも、「動物園に行く」、「高級レストランに行く」、「芋ほりに行く」など、どんな服を着ていけばいいのか迷ってしまうようなシチュエーションは、たくさんあります。

<div class="header">提案内容</div>
そこで、この研究では、画像認識AIと、画像生成AIをうまく組み合わせることで、シチュエーション名をキーワードとして与えると、そこに適した衣類を着用した画像を生成するシステムを開発しました。

このようなシステムを開発するうえで、ベースになったのは「AIの得意なことと、不得意なことの、非対称性」です。

具体的には、

- **生成AIの得意なタスク：** AIに人の写った画像を見せて「この画像は何をしている場面？」と聞くと、かなり高精度で正しい回答をする
- **生成AIの苦手なタスク：** AIに「○○している場面の画像を生成して」というと、画像全体としては自然だけれど、服装の組み合わせがおかしい画像が生成される

という状況を利用して、得意なタスクでたくさんの教師用データを作り、苦手なタスクに対応できるようにAIを再学習しました。

<div class="header">実験と分かったこと</div>
実際に、いくつかのシチュエーションを用意して、そのシチュエーションにあった画像を、様々な生成AIで出力して、被験者に比較してもらいました。

実験結果から、提案手法では、「確かにそのシチュエーションにあう、無難なコーディネート」が生成されることがわかりました。


![図](/assets/img/researches/oeICMR2026/oe_method.webp "画像のキャプショニングが簡単なのに対し、画像の生成が困難なことを利用したモデルの学習と検索。シチュエーションテキストからそれに適した服装の着用画像を生成。")


## 文献情報
- タイトル：
    - Asymmetric Pipeline for Dataset Construction and Situation-Aware Generative Outfit Retrieval Leveraging Differences in Task Difficulty
- 著者：
    - Yuma Oe, Katsumi Tanaka, Yoshiyuki Shoji
- 書誌情報：
    - Proc. of the 16th ACM International Conference on Multimedia Retrieval (ICMR 2026), to apperar, 2026
<!-- - [掲載サイト](https://doi.org/10.1007/978-3-032-11976-6_5) -->