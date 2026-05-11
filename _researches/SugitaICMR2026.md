---
layout: research
title: "こんな画像を生成するには、どんなAIを組み合わせるべき？ちょい足し検索"
description: "ICMR2026「Which LoRA Should Be Merged Next? Retrieving an Additional LoRA from a Target Image」"
date: 20260511
thumbnail: "/assets/img/researches/sugitaICMR2026/thumb.webp"
title_en: "Which LoRA should be marged next? Additional LoRA Retrieval"
---

<div class="catch">
「あと1つ、マージするべき画像生成LoRA」を検索可能に使用！
</div>
この研究では、複数のLoRA（画像生成AIに、特定の画風や特徴を与えるためのアダプタ）を使って画像を生成する際に、「あと1つ、ちょい足しするべきLoRA」を検索可能にする手法について提案しています。


<div class="header">研究背景</div>
近年では、良くも悪くも、画像生成AIが一般に広く普及してきており、みんなが高度な画像生成AI利用をするようになってきています。
その中でも特によく用いられる技術が、特定の画風や画像特徴を画像生成AIに持たせるアダプタである「LoRA」です。
「LoRA」は、複数を組み合わせて利用することが一般的で、たとえば「ゴッホ風LoRA」と「浮世絵風LoRA」を組み合わせると、あたかもゴッホが描いた浮世絵のような画像が生成されます。

このようなLoRAは、現状では、勝手にアップロードした利用者がつけた説明文や、タグからしか検索することができませんでした。
･･･一方で、複数のLoRAを組み合わせて使いたい場合、2つ目以降のLoRAは、うまくキーワードで探せません。
「ゴッホ風のLoRAを使って生成したこの画像を、もう少しダークな雰囲気にしたいんだけど…」と思ったとして、「少しダークな雰囲気にする用LoRA」などは存在しません。
そのため、さまざまなLoRAを順次適用していって、「たまたま合成したらダークなイメージになるLoRA」を見つける必要があります。

こうした「複数のLoRAの組み合わせを探す」という基盤技術は、画像生成AIの利用や勝手な学習が行われたLoRAの発見においてとても重要なのですが、いまだに確立されていません。

<div class="header">提案内容</div>
そこでこの研究では、「複数のLoRAを組み合わせて、任意の画風の画像を生成する」ことを可能にするための第1歩として、「現在利用中のLoRAと、理想の画風をもつ画像を入力すると、それに足すべきLoRAを1つ推薦する」という検索アルゴリズムを開発しました。

そのために、

- 大量のLoRAを収集して、
- 2つのLoRAを総当たりで組み合わせて画像データセットを作り、
- ある画像が、与えられた2つのLoRAで生成されたであろう確率を推定する

というデータセット作成と分類モデルの学習を行いました。
こうして学習した分類機に、今使っているLoRAと、ちょい足しすべきか悩んでいるLoRAを与えると、理想のスタイルをもつ画像を生成可能にできそうかどうかを判別できます。
候補のLoRAを次々にこの分類機にかけていけば、追加するべき順に、候補LoRAをランキングできます。

<div class="header">実験と分かったこと</div>
実験では、実際にたくさんのLoRAから無作為に選ばれた2つのLoRAを使って大量の画像を生成して、

- 本当にその画像を生成するのに使われたLoRAのペアを正しく分類できたかの評価、
- 検索エンジンとして使った際に、上位にその画像に使われたLoRAがランキングできていたかの評価、
- 実際に2つのLoRAをマージして生成した画像が、理想の画像地近い画風だったかの人手評価

をそれぞれ実施しました。

実験結果から、このような分類機を使った検索モジュールは、確かに「組み合わせたらその画像を生成できそうなLoRA」を発見可能でした。

･･･一方で、今回の手法は、計算コストが重すぎるため、実用的ではなないかもしれないということも、わかりました。

![図](/assets/img/researches/sugitaICMR2026/overview.webp "LoRAのIDを2-hotベクトルとして表し、画像と一緒に分類機に入力")
実際の分類機の構造。
2つのLoRAのIDと、1つの画像特徴量を入力すると、0-1で「この画像が、それら2つのLoRAで作られたどうか」を判定。確率の高い順に、LoRAを並び替えたら、検索ランキングとして使える。

## 文献情報
- タイトル：
    - Which LoRA Should Be Merged Next? Retrieving an Additional LoRA from a Target Image
- 著者：
    - Daichi Sugita, Huu-Long Pham, Makoto P. Kato, Hiroaki Ohshima, Sumio Fujita, Yoshiyuki Shoji
- 書誌情報：
    - Proc. of the 16th ACM International Conference on Multimedia Retrieval (ICMR 2026), to apperar, 2026
<!-- - [掲載サイト](https://doi.org/10.1007/978-3-032-11976-6_5) -->