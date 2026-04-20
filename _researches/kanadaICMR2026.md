---
layout: research
title: "画像生成AIの類似度を、AIの内部パラメータから計算可能にしよう！"
description: "ICMR2026「Retrieval of LoRA Models based on Layer-Wise Weight Embedding without Metadata」"
date: 20260420
thumbnail: "/assets/img/researches/kanadaICMR2026/thumb.png"
title_en: "Finding Similar Image AI by Their Internal Parameters"
---

<div class="catch">
画像生成AI同士の類似度を、説明文や出力例などを使わずに計算可能に！
</div>
この研究では、画像生成AI用のアダプタ（LoRA）を検索可能にするための基礎技術として、LoRA内部の重みだけからそのLoRAをベクトルで表す方法について提案しています。




<div class="header">研究背景</div>
現在、画像生成AIに追加することで特定の画風に特化させるためのアダプタである「LoRA」がたくさん学習され、共有されるようになってきています。
たとえば、civitaiというサイトでは、勝手に学習された数百万件のLoRAアダプタが公開されています。
こうしたたくさんのLoRAは、現状では、投稿者が任意でつけたタグや説明文からテキスト検索することしかできませんでした。

公開中のLoRAには、正しいタグや説明文がついていないこともよくあります。
その場合、「こういう画風の画像を生成したい」という利用者や、「自分の画像を勝手に学習したLoRAが配られているのでは？」と心配するアーティストは、該当するLoRAを探すことができません。
すべてのLoRAをダウンロードして、実際に画像を生成させてみて、「このLoRAは自分が探していたLoRAだ！」と判断していくのは、現実的ではありません。

<div class="header">提案内容</div>
そこで、この研究では、LoRAのファイル本体をそのまま入力すると、その特徴を表したベクトルに変換する**エンコーダ（ベクトル変換器）**を作成しました。
この変換器は、LoRAに付随するメタデータ（タグや、説明文や、サンプル画像など）を一切使わずにベクトル化することができます。
LoRAがベクトルとして表せたら、「ベクトル同士の距離」として類似度を測ったり、既存のベクトル検索アルゴリズムでLoRAを検索可能になります。

このようなエンコーダを実現するために、

1. LoRAファイル内の「重み」をそのまま次元圧縮して、とりあえずシードとなるベクトルを作り、
2. 「似た画像を生成するLoRAどうしは、ベクトル空間内でも近くなるだろう」という仮定の下、ベクトルに重みづけ

をするシステムを作成しました。
こうすることで、メタデータのない未知のLoRAモデルが単体で渡されたとしても、それと似た画像を出力しそうな別のLoRAを発見可能になります。

このLoRAのベクトル化は、画像生成AIの利用者の検索だけでなく、個人の権利を侵害したLoRAの検出にも使える、きわめて重要な基幹技術です。

<div class="header">実験と分かったこと</div>
実際に、複数のモデルにサンプル画像を変換させて、データセットを作りました。
こうして作ったデータセットについて、LoRAモデル同士がベクトルとして類似度が近い場合に、その変換結果画像も似るのかどうかを、画像分析アルゴリズムと人手で、それぞれ評価しました。

実験結果から、実際に提案手法で、似た画像を出力するモデル同士を正しく「モデル同士が近い」と判定できるようなベクトル化ができていることが確認できました。
今後は、このベクトルを使って、キーワードからAIモデルを検索可能にしたり、著作権侵害AIを検出可能にすることが期待できます。


![図](/assets/img/researches/kanadaICMR2026/kanada_method.png "モデルの内部パラメータをそのまま次元圧縮し、そのあとで距離学習で意味のあるベクトルに変換")


## 文献情報
- タイトル：
    - Retrieval of LoRA Models based on Layer-Wise Weight Embedding without Metadata
- 著者：
    - Yuro Kanada, Yuma Oe, Huu-Long Pham, Makoto P. Kato, Hiroaki Ohshima, Sumio Fujita, Yoshiyuki Shoji
- 書誌情報：
    - Proc. of the 16th ACM International Conference on Multimedia Retrieval (ICMR 2026), to apperar, 2026
<!-- - [掲載サイト](https://doi.org/10.1007/978-3-032-11976-6_5) -->