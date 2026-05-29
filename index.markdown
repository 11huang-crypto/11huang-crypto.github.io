---
layout: home
---

<section class="hero">
  <div class="container">
    <h1>Welcome to 11huang-crypto</h1>
    <p>探索区块链技术，分享加密货币见解，一起进入Web3的世界</p>
    <a href="#posts" class="cta-button">开始探索</a>
  </div>
</section>

<section class="features">
  <div class="container">
    <h2 class="section-title">特色内容</h2>
    <div class="cards">
      <div class="card">
        <div class="card-icon">📊</div>
        <h3>市场分析</h3>
        <p>深入分析加密货币市场趋势，提供专业的投资见解和策略建议。</p>
      </div>
      <div class="card">
        <div class="card-icon">⚡</div>
        <h3>技术解析</h3>
        <p>解读区块链底层技术，探讨智能合约、DeFi、NFT等热门话题。</p>
      </div>
      <div class="card">
        <div class="card-icon">📚</div>
        <h3>学习资源</h3>
        <p>从入门到精通，为您整理最优质的区块链学习资料和教程。</p>
      </div>
    </div>
  </div>
</section>

<section id="posts" class="posts-section">
  <div class="container">
    <h2 class="section-title">最新文章</h2>
    <div class="posts">
      {% for post in site.posts %}
      <article class="post-card">
        <div class="post-image">💎</div>
        <div class="post-content">
          <p class="post-meta">{{ post.date | date: "%Y年%m月%d日" }}</p>
          <h3 class="post-title">{{ post.title }}</h3>
          <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 20 }}</p>
          <a href="{{ post.url }}" class="read-more">阅读更多 →</a>
        </div>
      </article>
      {% endfor %}
    </div>
  </div>
</section>