---
layout: page
title: Research
permalink: /research/
description: "静岡大学情報学部行動情報学科で情報アクセス技術の研究を行っている「莊司慶行研究室」で行われた過去の研究について、その一部を紹介します。"

---


<style>
    div.topic{
        background-color: #FFFFFF;
        border-radius: 1%;
        padding: 2%;
        margin: 2%;
    }

    div.paper{
        background-color: #F5F5F5;
        border-radius: 1%;
        padding: 2%;
        margin: 2%;  
    }

    details {
      border: 2px solid #2196F3;
      border-radius: 8px;
      padding: 10px;
      margin: 10px 0;
      background-color: #f9f9f9;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
      cursor: pointer;
    }

    
    summary {
      font-weight: bold;
      font-size: 1.1rem;
      padding: 5px;
      outline: none;
      display: list-item;
    }

    summary:hover {
      background-color: #e0f7fa;
      border-radius: 6px;
    }


    details[open] summary {
      color: #0d47a1;
    }

    .box {
    display: flex;
    justify-content: left;
    align-items: left;
    }

    details[open] {
      background-color: #e3f2fd;
      transition: background-color 0.3s, border-color 0.3s;
    }

    img.box {
    width: 100px;
    height: 100px;
    object-fit: cover;
    float: left;
    padding-right: 5%;
    }

    div.paper{
        overflow: hidden;
    }

    .paper::after {
        content: "";
        display: block;
        clear: both; /* floatの要素をクリア */
    }

    span.topic{
        color: #0d47a1;
        font-weight: bold;
    }

    /* ===== Sticky Note Research Topics ===== */

    .research_topics{
      display:grid;
      grid-template-columns: repeat(2, minmax(0,1fr));
      gap:20px;
      margin:20px 0;
      align-items:start;
    }
    @media (max-width: 720px){ .research_topics{ grid-template-columns: 1fr; } }

    .research_topics details{
      position:relative;
      background:#fffbd1;
      border:1px solid rgba(0,0,0,.05);
      border-radius:10px;
      box-shadow:0 10px 20px rgba(0,0,0,.06), 0 2px 6px rgba(0,0,0,.05);
      padding:14px 12px;
      transform-origin:50% 10%;
      transition:transform .2s ease, box-shadow .2s ease;
      overflow:hidden;
      align-self:start;
    }
    .research_topics details:nth-child(5n+1){ background:#fffbd1; }
    .research_topics details:nth-child(5n+2){ background:#e9ffd8; }
    .research_topics details:nth-child(5n+3){ background:#ffe9ec; }
    .research_topics details:nth-child(5n+4){ background:#eaf3ff; }
    .research_topics details:nth-child(5n+5){ background:#f9e8ff; }

    .research_topics details:nth-child(3n){ transform:rotate(-1.4deg); }
    .research_topics details:nth-child(4n){ transform:rotate(1.8deg); }
    .research_topics details[open]{ transform:rotate(0deg); box-shadow:0 14px 28px rgba(0,0,0,.1), 0 4px 10px rgba(0,0,0,.08); }

    /* マスキングテープ風 */
    .research_topics details::before{
      content:""; position:absolute; top:-10px; left:50%;
      width:100px; height:22px; transform:translateX(-50%) rotate(-2deg);
      background:repeating-linear-gradient(45deg, rgba(255,255,255,.8) 0 6px, rgba(240,240,240,.8) 6px 12px);
      border-radius:4px; box-shadow:0 3px 5px rgba(0,0,0,.08); pointer-events:none;
    }

    /* summary部分をグリッドに */
    .research_topics summary{
      list-style: none;
      cursor: pointer;
      display: grid;
      grid-template-columns: 1fr auto;
      grid-template-rows: auto auto;
      row-gap: 8px;
      align-items: start;
      margin:0; padding:0;
    }
    .research_topics summary::-webkit-details-marker{ display:none; }

    .note-head{ display: contents; }
    .note-title{
      grid-column: 1 / 2;
      font-weight: 700;
      font-size: 1rem;
      line-height: 1.25;
      margin: 0;
    }
    .note-click{
      grid-column: 2 / 3;
      justify-self: end;
      align-self: start;
      font-size: .8rem;
      color: #0f766e;
      background: rgba(15,118,110,.06);
      padding: 2px 8px;
      border-radius: 999px;
      white-space: nowrap;
    }

    /* サムネは2列ぶち抜きで下段に常に表示 */
    .note-thumb{
      grid-column: 1 / 3;
      display:block;
      width:100%;
      aspect-ratio:16/9;
      object-fit:cover;
      border-radius:8px;
      background:#f2f5f9;
      margin:0;
      opacity:.95;
      transition:opacity .25s ease, transform .25s ease;
    }
    details:not([open]) .note-thumb{
      transform:scale(.99);
      opacity:.9;
    }

    /* 本文だけ“にゅるっ”展開 */
    .topic{
      max-height:0; overflow:hidden;
      transition:max-height .35s ease, opacity .25s ease, transform .25s ease;
      opacity:0; transform: translateY(-4px);
      margin-top:10px; border-top:1px dashed rgba(0,0,0,.2); padding-top:8px;
      font-size:.95rem; color:#333;
    }
    details[open] .topic{ max-height:1200px; opacity:1; transform:translateY(0); }

    .topic ul{ margin:6px 0 0 1.2em; }
    .topic strong{ color:#111; }

</style>

莊司研究室では、情報アクセス技術を中心に、本当にいろんなトピックで研究を行っています。

このページでは、主要な研究トピックの概要と、実際の研究事例を紹介します。


<h1>研究テーマ</h1>

  <div class="research_topics">
    <details>
      <summary>
        <div class="note-head">
          <span class="note-title">より現実世界での検索に近い情報検索</span>
          <span class="note-click">Click</span>
        </div>
        <img class="note-thumb" src="https://shoji-lab.github.io/assets/img/researches/topic_purpose.png" alt="">
      </summary>
      <div class="topic">
        <p><strong>現状のWeb情報検索は、不自然です。</strong></p>
        <p>現実世界で何か商品を探す際のことをイメージしてください。
        たとえば、新しいテレビを買うために、電気屋さんに行って、店員さんに自分の検索条件に見合ったテレビを探してもらう場合を考えます。
        この際には、多くの場合、「時代劇に適したテレビはどれ？」、「FPSのゲームに最適なテレビはどれ？」というように、自分の置かれた状況や、自分の目的を伝えることで検索を行っています。
        図書館で本を探す場合も、同様です。
        「○○という登場人物が、××する本を探してください」という検索は、一般的には行われません。
        検索とは、知らないことを調べるための行為であるため、調べたい対象を伝えることが出来ないからです。</p>

        <p>一方で、現在の多くのWeb検索エンジンでは、このような不自然な検索を、利用者に強いています。
        一般的な検索エンジンでは、「自分が最終的に見つけたいページに含まれていそうなキーワード」を、検索の入力としています。
        本来、知らないことを調べるための情報検索なのに、調べたいページに含まれていそうな単語を、自分で推測しないといけません。</p>

        <p>このような不自然な検索から利用者を解放するために、莊司研究室では、検索エンジンにより自由な入力を可能にするような検索アルゴリズムの研究をいくつも行っています。</p>
        <p>
        <span class="topic">研究事例：</span>
        <ul>
        <li>「目的」を入力とする場所やアイテムの検索</li>
        <li>「みんなの感想」を入力とするWebページ検索</li>
        </ul>
        などなど･･･
        </p>

      </div>
    </details>

    <details>
      <summary>
        <div class="note-head">
          <span class="note-title">記憶に残る情報アクセス技術</span>
          <span class="note-click">Click</span>
        </div>
        <img class="note-thumb" src="https://shoji-lab.github.io/assets/img/researches/topic_purpose.png" alt="">
      </summary>
      <div class="topic">
        <p><strong>Webで日常的に見た情報、なんにも身についてない！</strong></p>
        <p>
        現代人は、1日に4時間近くをWebの閲覧に充てているという調査報告があります。
        これは、テレビや雑誌、書籍などよりも長く、現代人が一番長時間接しているメディアはWebであるということができます。
        </p>

        <p>
        一方で、Webで得た情報は、記憶に残りづらいという指摘もされています。
        個人がWeb検索で入力するクエリのうち、4割は再訪問のためのクエリだと言われています。
        これには行きつけのサイトへの再訪問だけでなく、閲覧したけれど忘れてしまった情報への「調べなおし」のための再アクセスが多く含まれています。
        </p>

        <p>
        データに照らし合わせなくても、直感的に、普段のWebアクセスは長時間接している割に、何も身についていないと感じられます。
        たとえば、楽器を毎日4時間弾いていたら、1年も経ったらそれなりの腕前になります。
        映画を毎日2本見ていたら映画通ですし、毎日4時間筋トレしたら筋骨隆々になれるでしょう。
        ･･･それに比べて、Web閲覧は、どうでしょうか？
        何か、身についているでしょうか？
        </p>

        <p>
        莊司研究室では、こうした日常的なWeb閲覧に費やした時間を、少しでも有意義なものにするため、
        Webで見た情報を記憶に残し知識に定着させるための情報アクセス技術についても研究しています。
        </p>

        <p>
        <span class="topic">研究事例：</span>
        <ul>
        <li>その日のWeb閲覧履歴をカードにして整理したり、クイズにする記憶支援</li>
        <li>日常生活の中でWeb検索履歴と関連する施設に近づくと通知が出るシステム</li>
        </ul>
        などなど･･･
        </p>

      </div>
    </details>

    <details>
      <summary>
        <div class="note-head">
          <span class="note-title">多人数の意見を集約した情報検索技術</span>
          <span class="note-click">Click</span>
        </div>
        <img class="note-thumb" src="https://shoji-lab.github.io/assets/img/researches/topic_purpose.png" alt="">
      </summary>
      <div class="topic">
        <p><strong>レビューしか判断材料がないけど、レビューを全部読むのは、不可能！</strong></p>
        <p>
        近年ではインターネット上のレビュー情報から意思決定をする機会が増えています。
        たとえば観たい映画を探す場合、公式サイトにはあまり情報が載っていないので、視聴者のレビューを参考に、その映画を見るかどうかを判断します。
        また商品情報サイトでは、スペックシートを読んだところで、その実際の使い心地などは分からないので、
        結局レビューを参考にアイテムの購入を判断することが多いです。
        </p>
        <p>
        このように日常的に意思決定に使われるレビューですが、現状では、たくさんあるレビューを検索したり、要約したり、使いやすくする技術は未発達です。
        たとえば、「どんでん返しのすごい映画」を探したい場合、どうやってレビューから映画を探せばいいでしょうか･･･？
        多くの場合、レビュー中で「どんでん返し」という単語は使われず、「終盤に驚きの展開があった」、「思わず観終わった後に2週目に突入した」など、さまざまな書かれ方をします。
        また、100人が「終盤、やや驚いた」と評価している映画と、5人が「終盤の展開に、人生で一番驚いた」と評している映画だったら、どちらがより「どんでん返し」度合いの高い映画でしょうか。
        </p>
        <p>
        莊司研究室では、レビューや、投稿レシピ、ソーシャルメディアの投稿などの、「そのまま単体だと役に立たないけれど、集めると意味をもちはじめる」情報を集約して、活用できるようにする研究を進めています。
        </p>

        <p>
        <span class="topic">研究事例：</span>
        <ul>
        <li>投稿レビューを集計しての「○○な映画」のランキング</li>
        <li>SNSからの「○○を買った人は、そのあと××をしがち」という事例の抽出</li>
        </ul>
        などなど･･･
        </p>

      </div>
    </details>

    <details>
      <summary>
        <div class="note-head">
          <span class="note-title">中身まで読みたくなるような情報提示</span>
          <span class="note-click">Click</span>
        </div>
        <img class="note-thumb" src="https://shoji-lab.github.io/assets/img/researches/topic_purpose.png" alt="">
      </summary>
      <div class="topic">
        <p><strong>SNSで流れてきたリンク、タイトルだけ読んでクリックしない</strong></p>
        <p>今日では、「このページを読んでみたら？」「この商品はどう？」と、ウェブサイトへのリンクを提示されることが多くなってきています。
        例えばソーシャルメディアで、タイトル付きのニュース記事をシェアするのは当たり前の行為ですし、近年では推薦アルゴリズムが読むべきニュースや買うべき商品を推薦してきます。</p>

        <p>･･･一方で、ただニュースタイトルが書かれただけのリンクや、商品名が書かれただけのリンクだと、人はわざわざクリックしてそのサイトまで行こうとは思いません。せっかく高度な検索・推薦アルゴリズムを作ったとしても、それらのリンク先に誰もアクセスしなかったら、そのアルゴリズムは無駄になってしまいます。</p>

        <p>そこで、検索や推薦の結果を、真に見てもらえるようにするために、リンクのテキストをその人に合わせて書き換えたり、商品名でなくキャッチコピーやその商品の魅力に置き換えることを考えます。例えば、「巨人が阪神に負けた」というニュースがあった際に、巨人ファンには「巨人、快勝！」と伝えると思わずクリックしたくなりますし、阪神ファンには「阪神、健闘するも惜敗」と伝えたほうが読んでもらえそうです。同様に、「ISO 25600のカメラ」と言われるより、「夜でも顔がくっきり撮れるカメラ」と言われた方が、クリックしやすいです。</p>

        <p>
        莊司研究室では、検索結果や推薦結果を、知識のない人でも内容を理解しやすく、読みたいと思わせるための情報提示やデザインの研究をしています。
        大規模言語モデルや様々なデータを使って、ページ内容を要約したり、記述を変換したり、情報が必要な人に届くようにするアルゴリズムを開発しています。
        </p>

        <p>
        <span class="topic">研究事例：</span>
        <ul>
        <li>商品スペックからのキャッチコピー生成</li>
        <li>個人に合わせたニュースタイトル変換</li>
        </ul>
        などなど･･･
        </p>

      </div>
    </details>


        <details>
      <summary>
        <div class="note-head">
          <span class="note-title">現実世界での情報アクセス技術（ミュージアム情報アクセス）</span>
          <span class="note-click">Click</span>
        </div>
        <img class="note-thumb" src="https://shoji-lab.github.io/assets/img/researches/topic_purpose.png" alt="">
      </summary>
      <div class="topic">
        <p><strong>なんとなく博物館に行くだけでは、あんまり知識が得られない。</strong></p>
        <p>
        情報アクセスは、なにも、コンピュータやWebの中に限られた話ではありません。
        現実世界は情報に溢れており、人々は当たり前のように、日夜、情報を獲得しています。
        学校や図書館から、街の掲示板まで、ありとあらゆる場所で情報アクセスが行われています。
        </p>
        <p>
        莊司研究室では、特に情報アクセス技術による支援が重要な領域として、ミュージアムにおける情報アクセス支援の研究を行っています。
        具体的には、博物館で展示物を観賞した際に、それがより深く知識に定着し、観賞体験が有意義になるよう、情報系の技術を使ってサポートします。
        </p>
        <p>
        美術館や博物館といったミュージアムには、さまざまな人たちが訪れます。
        その中には、学校の行事で連れて来られた人や、タダ券をもらったから来たという人など、自発的な理由で訪問していない人が多く含まれます。
        そういった人たちでも、積極的にミュージアムを鑑賞できるようにして、展示物に興味を持ち、覚えて貰うためのシステムについて研究しています。
        </p>

        <p>
        <span class="topic">研究事例：</span>
        <ul>
        <li>ガイド端末の操作ログを分析して、観賞体験を1枚のポストカードに変換</li>
        <li>個人の興味のあるまだ見ぬ展示物を探させる「宝探しゲーム」の自動生成</li>
        </ul>
        などなど･･･
        </p>

      </div>
    </details>


        <details>
      <summary>
        <div class="note-head">
          <span class="note-title">その他の研究</span>
          <span class="note-click">Click</span>
        </div>
        <img class="note-thumb" src="https://picsum.photos/seed/review/600/338" alt="">
      </summary>
      <div class="topic">
        <p><strong>面白ければ、割と、何でも</strong></p>
        <p>それ以外でも、たくさんの情報アクセスに関連する（たまに、関連しない）研究を行ってきています。</p>
        <span class="topic">研究事例：</span>
        <ul>
        <li>音ゲーの操作ログ分析によるトレーニング譜面の自動生成</li>
        <li>VR空間内でのWeb情報検索</li>
        </ul>
        などなど･･･
      </div>
    </details>
  </div>





<h1>実際の研究事例紹介</h1>
{% assign sorted_researches = site.researches | sort: 'date' | reverse %}
{% for item in sorted_researches %}
<div class=paper>
<img class="box" src="{{ item.thumbnail }}" loading="lazy">
  <p><strong><a href="{{ item.url }}">{{ item.title }}</a></strong></p>
  <p>{{ item.description }}</p>
</div>
{% endfor %}

