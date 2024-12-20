---
layout: research
title: "博物館鑑賞を「個人の興味に合わせた宝探しゲーム」にしてしまおう！"
description: "ICADL 2023 「Personalized Treasure Hunt Game for Proactive Museum Appreciation by Analyzing Guide App Operation Log」"
date: 20231220
thumbnail: "/assets/img/researches/icadl2023/minpakuthumb.png"
---

この研究では、博物館のガイド端末のログを解析することでその人個人の興味を推定して、個人に合わせた「宝探しゲーム」を生成するシステムを作成しています。

漫然と目的を持たずに、順路通りにミュージアムを観賞すると、鑑賞した内容が知識として定着しない現象が知られています。
そのため、多くの博物館などでは「スタンプラリー」などで、自発的に展示物を探すような、積極的な観賞を促す仕組みを導入しています。
一方で、博物館側に用意されたスタンプラリーが、その人個人の興味に合致する内容であるとは限りません。
興味のない展示物について覚えても、あまりうれしくないかもしれません。

そこで、この研究では、はじめにその人がどのような展示物に興味がありそうかを、ガイド端末の操作ログから推定します。
そして、アルゴリズムを使って、「その人が興味を持ちそうだけれど、まだ見ていない展示物」を推定します。
推定された展示物を「お宝」として、少ないヒントから目的の展示物を探す「宝探しゲーム」をプレイ可能にしました。

実験から、ゲームはプレイヤーに好意的に受け止められ、実際に宝探しの対象になった展示物は深く記憶に刻まれていることが分かりました。


![図](/assets/img/researches/icadle2023/hints.png "クイズ画面")
実際のクイズ画面（ヒントボタンを押して、隠れた情報を開示）。

![図](/assets/img/researches/icadle2023/stamps.png "スタンプ集め画面")
なるべく少ないヒントをもとに、すべてのスタンプをゲット！


## 文献情報
- タイトル：
    - Personalized Treasure Hunt Game for Proactive Museum Appreciation by Analyzing Guide App Operation Log
- 著者：
    - Jinsong Yu, Shio Takidaira, Tsukasa Sawaura, Yoshiyuki Shoji, Takehiro Yamamoto, Yusuke Yamamoto, Hiroaki Ohshima, Kenro Aihara, Noriko Kando
- 書誌情報：
    - Proc. of The 25th International Conference on Asia-Pacific Digital Libraries (ICADL 2023), pp. 30 – 45, 2023
- [掲載先（Springer）](https://doi.org/10.1007/978-981-99-8088-8_3)