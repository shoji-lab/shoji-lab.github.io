---
layout: research
title: "任意のキーワードに対して、レビュー中に現れる多様な言い換え表現を発見しよう"
description: "Rinton Press 論文誌 JDI 「Doc2Vec-based Approach for Extracting Diverse Evaluation Expressions from Online Review Data」"
date: 20221212
thumbnail: "/assets/img/researches/JDI2022kurihara/thumb.png"
---

<div class="catch">
人は泣ける映画を見た時に、レビューになんて書く？
</div>

<div class="header">研究背景</div>
人は泣ける映画を見た際に、レビュー中にそのまま「泣ける映画だ。」という風には書きません。
多くの場合、「ハンカチがぐしょぐしょになった」、「翌日、メイクが乗らなかった」など、さまざまな比喩表現を使って感動を表現します。
そのため、「泣ける」と関連する映画レビューを検索することが、困難になっています。

レビューサイトは、比喩表現や、さまざまな言い換えに溢れています。
こうしたたくさんのレビューから、キーワードと関連するレビューを探してくるのは、難しい問題です。


<div class="header">提案内容</div>
このような問題を解決するために、この研究では、任意のキーワードを与えると、それの言い換えとなりそうな表現を、なるべく多様にたくさん生成する技術を提案しています。

具体的なアプローチとして、文書埋め込み手法「Doc2Vec」を改良し、2つの工夫を取り入れることで多様な評価表現を抽出可能にしました：

- 文脈の拡張： 「ターゲットトピック」という概念を導入し、同じ映画に関連するレビュー文を文脈として使用。短い文でも十分な情報を学習できるようにしました。
- クエリ拡張： ユーザーが入力したクエリを、類義語などであらかじめ拡張することで、より多様な表現を発見可能にしました。

こうすることで、たとえばクエリ「泣ける映画」に対して「涙が止まらない」や「ハンカチがボロボロになった」といった多様な表現を関連付けることが可能になりました。

<div class="header">実験と分かったこと</div>
Yahoo!映画のレビューを使用した実験では、1,200万件以上のレビュー文からデータを抽出し、提案手法を評価しました。

その結果、ターゲットトピックを活用した改良版Doc2Vec（TTA-D2V）が、従来手法よりも関連性が高く多様な表現を抽出できることが確認されました。

一方で、クエリ拡張を行うと表現の多様性が向上する一方で、検索結果の精度が若干低下するトレードオフも見られました。


![図](/assets/img/researches/JDI2022kurihara/kuriharaD2V.png "実際の手法")
Doc2Vecという手法を拡張し、誰か別の人が「泣ける」といった映画には関連する表現が含まれがちだと仮定して言い換えを発見。


## 文献情報
- タイトル：
    - Doc2Vec-based Approach for Extracting Diverse Evaluation Expressions from Online Review Data
- 著者：
    - Kosuke Kurihara, Yoshiyuki Shoji, Sumio Fujita, Martin J. Dürst
- 書誌情報：
    - Journal of Data Intelligence (JDI), Vol.3, No.2, pp. 441 – 459, 2022.
- [ダウンロード（JDI）](https://doi.org/10.26421/JDI3.4-3)