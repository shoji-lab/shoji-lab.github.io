---
layout: page
title: Research
permalink: /en/research/
description: "This page introduces selected past research conducted in the Shoji Laboratory, which studies information access technologies at the Department of Behavioral Informatics, Faculty of Informatics, Shizuoka University."


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
At the Shoji Laboratory, we conduct research on a wide variety of topics centered on information access technologies.

This page provides an overview of our main research themes and selected examples of our work.

Our publications are summarized on <a href="https://shoji-lab.jp/">Shoji’s personal website</a>.

<h1>Research Themes</h1>

<div class="research_topics">
  <details>
    <summary>
      <div class="note-head">
        <span class="note-title">Information Retrieval Closer to Real-World Search</span>
        <span class="note-click">Click</span>
      </div>
      <img class="note-thumb" src="https://shoji-lab.github.io/assets/img/researches/topic_purpose.png" alt="">
    </summary>
    <div class="topic">
      <p><strong>Today’s web search is often unnatural.</strong></p>

      <p>
        Think about how you search for something in the real world. For example, when you go to an electronics store to buy a new TV and ask a staff member for recommendations, you typically describe your <em>situation</em> and <em>purpose</em>, such as:
        “Which TV is best for watching period dramas?” or “Which TV is suitable for FPS games?”
        The same applies when looking for a book in a library—you rarely search by specifying exact entities or keywords in advance.
        Search is fundamentally an act of learning about something unknown, so users cannot always describe the target using the “right” terms.
      </p>

      <p>
        However, many web search engines require users to perform exactly that kind of unnatural search.
        Users are expected to input “keywords that are likely to appear on the page they ultimately want to find.”
        In other words, even though search is supposed to help you discover what you do not know, you still need to guess the words that might appear in the relevant pages.
      </p>

      <p>
        To free users from such unnatural interactions, the Shoji Laboratory studies retrieval algorithms that allow more flexible and expressive queries.
      </p>

      <p>
        <span class="topic">Examples:</span>
        <ul>
          <li>Searching for places or items using a user’s <em>purpose</em> as input</li>
          <li>Web page search using “people’s impressions” as input</li>
        </ul>
        …and more.
      </p>
    </div>
  </details>

  <details>
    <summary>
      <div class="note-head">
        <span class="note-title">Information Access That Sticks in Memory</span>
        <span class="note-click">Click</span>
      </div>
      <img class="note-thumb" src="https://shoji-lab.github.io/assets/img/researches/topic_memory.png" alt="">
    </summary>
    <div class="topic">
      <p><strong>So much daily web browsing—yet it hardly becomes knowledge.</strong></p>

      <p>
        Some reports suggest that people spend close to four hours per day browsing the web.
        Compared with TV, magazines, or books, the web may be the medium people engage with the most.
      </p>

      <p>
        At the same time, it has been pointed out that information obtained on the web is difficult to retain.
        It is said that a large fraction of web queries are “revisitation queries.”
        These include not only returning to familiar sites, but also re-searching information that was previously read but later forgotten.
      </p>

      <p>
        Even without relying on data, many people have an intuitive sense that web browsing leaves little lasting learning despite the time invested.
        If you practiced an instrument for four hours every day, you would become fairly skilled within a year.
        If you watched two films every day, you would become a movie enthusiast.
        If you trained for four hours daily, you would become physically strong.
        …But what about daily web browsing?
        Does it really leave you with lasting skills or knowledge?
      </p>

      <p>
        The Shoji Laboratory studies information access technologies that help transform everyday web experiences into more meaningful learning,
        by supporting memory and knowledge consolidation from what users read online.
      </p>

      <p>
        <span class="topic">Examples:</span>
        <ul>
          <li>Organizing daily browsing history into “cards,” or turning it into quizzes to support recall</li>
          <li>Notifying users when they approach real-world places related to their past web searches</li>
        </ul>
        …and more.
      </p>
    </div>
  </details>

  <details>
    <summary>
      <div class="note-head">
        <span class="note-title">Information Retrieval from Aggregated Opinions</span>
        <span class="note-click">Click</span>
      </div>
      <img class="note-thumb" src="https://shoji-lab.github.io/assets/img/researches/topic_review.png" alt="">
    </summary>
    <div class="topic">
      <p><strong>Reviews are often the only evidence—but reading them all is impossible.</strong></p>

      <p>
        In recent years, people increasingly rely on online reviews to make decisions.
        For example, when choosing a movie to watch, official sites often provide limited information, so viewers consult audience reviews.
        Similarly, for many products, a spec sheet alone cannot convey real-world usability, so purchase decisions often depend on reviews.
      </p>

      <p>
        Although reviews are widely used in everyday decision-making, technologies for searching, summarizing, and making large volumes of reviews usable are still underdeveloped.
        For example, if you want to find “a movie with an amazing plot twist,” how can you search for it through reviews?
        In many cases, reviewers do not use the literal phrase “plot twist”; instead they describe it in many ways, such as “an unexpected turn near the end” or “I immediately started rewatching after finishing.”
        Moreover, consider two movies: one where 100 people say “the ending was somewhat surprising,” and another where 5 people say “it was the most shocking ending of my life.”
        Which one is more “plot-twist-heavy”?
      </p>

      <p>
        The Shoji Laboratory studies methods to aggregate and leverage information that may be unhelpful in isolation but becomes meaningful at scale,
        such as reviews, user-submitted recipes, and social media posts.
      </p>

      <p>
        <span class="topic">Examples:</span>
        <ul>
          <li>Ranking “movies that are X” by aggregating review content</li>
          <li>Mining cases like “people who bought X tend to do Y afterward” from social media</li>
        </ul>
        …and more.
      </p>
    </div>
  </details>

  <details>
    <summary>
      <div class="note-head">
        <span class="note-title">Information Presentation That Makes You Want to Read Further</span>
        <span class="note-click">Click</span>
      </div>
      <img class="note-thumb" src="https://shoji-lab.github.io/assets/img/researches/topic_web.png" alt="">
    </summary>
    <div class="topic">
      <p><strong>Links in social feeds are often ignored if only the title is shown.</strong></p>

      <p>
        Today, users are frequently presented with links: “How about reading this page?” or “What about this product?”
        Sharing news links with titles on social media is common, and recommendation algorithms suggest what news to read or what products to buy.
      </p>

      <p>
        However, if a link only shows a headline or a product name, people often do not bother clicking.
        Even if we build sophisticated retrieval and recommendation algorithms, they become ineffective if no one actually visits the suggested pages.
      </p>

      <p>
        One approach is to rewrite link text to match the user, or to replace a bare product name with a compelling message that highlights its appeal.
        For example, suppose there is a news story about a baseball game.
        A Giants fan might be more likely to click on “Giants dominate!” while a Tigers fan might respond better to “Tigers fought hard but narrowly lost.”
        Likewise, “ISO 25600 camera” may be less clickable than “a camera that captures clear faces even at night.”
      </p>

      <p>
        The Shoji Laboratory studies information presentation and design that make search and recommendation results easier to understand and more attractive to read, even for non-experts.
        Using large language models and diverse data sources, we develop algorithms that summarize content, transform descriptions, and deliver information in a way that reaches the people who need it.
      </p>

      <p>
        <span class="topic">Examples:</span>
        <ul>
          <li>Generating catchphrases from product specifications</li>
          <li>Personalized rewriting of news headlines</li>
        </ul>
        …and more.
      </p>
    </div>
  </details>

  <details>
    <summary>
      <div class="note-head">
        <span class="note-title">Information Access in the Physical World (Museum Information Access)</span>
        <span class="note-click">Click</span>
      </div>
      <img class="note-thumb" src="https://shoji-lab.github.io/assets/img/researches/topic_museum.png" alt="">
    </summary>
    <div class="topic">
      <p><strong>Simply visiting a museum casually does not always lead to much learning.</strong></p>

      <p>
        Information access is not limited to computers or the web.
        The physical world is filled with information, and people continuously acquire it in everyday life—from schools and libraries to bulletin boards in town.
      </p>

      <p>
        The Shoji Laboratory focuses on museums as a particularly important domain where information access support can make a difference.
        We use information technologies to help visitors engage more deeply with exhibits, consolidate what they learned into lasting knowledge, and make the viewing experience more meaningful.
      </p>

      <p>
        Museums attract a wide range of visitors.
        Many visitors come for non-self-motivated reasons—for example, school trips or free tickets.
        We study systems that help such visitors view exhibits more actively, become interested, and remember what they experienced.
      </p>

      <p>
        <span class="topic">Examples:</span>
        <ul>
          <li>Analyzing interaction logs from a guide device and converting the viewing experience into a single “postcard”</li>
          <li>Automatically generating a “treasure-hunt game” that encourages visitors to find exhibits they have not yet seen but may like</li>
        </ul>
        …and more.
      </p>
    </div>
  </details>

  <details>
    <summary>
      <div class="note-head">
        <span class="note-title">Other Projects</span>
        <span class="note-click">Click</span>
      </div>
      <img class="note-thumb" src="https://shoji-lab.github.io/assets/img/researches/topic_other.png" alt="">
    </summary>
    <div class="topic">
      <p><strong>If it is interesting, we are open to it.</strong></p>
      <p>
        Beyond the themes above, we have explored many other projects related (and occasionally not directly related) to information access.
      </p>
      <span class="topic">Examples:</span>
      <ul>
        <li>Automatically generating training charts by analyzing interaction logs from rhythm games</li>
        <li>Web information retrieval within VR environments</li>
      </ul>
      …and more.
    </div>
  </details>
</div>

<h1>Selected Research Examples</h1>
{% assign sorted_researches = site.researches | sort: 'date' | reverse %}
{% for item in sorted_researches %}
<div class=paper>
<img class="box" src="{{ item.thumbnail }}" loading="lazy">
  <p><strong><a href="{{ item.url }}">{{ item.title }}</a></strong></p>
  <p>{{ item.description }}</p>
</div>
{% endfor %}