---
layout: home
---

<section class="hero">
  <div class="container">
    <h1>11huang-crypto</h1>
    <p>个人技术博客 | 学习笔记 | 项目记录</p>
    <a href="#posts" class="cta-button">查看文章</a>
  </div>
</section>

<section id="projects" class="features">
  <div class="container">
    <h2 class="section-title">博客内容</h2>
    <div class="cards">
      <div class="card">
        <div class="card-icon">📝</div>
        <h3>技术文章</h3>
        <p>记录学习 Jekyll、GitHub Pages、Web开发的技术心得和经验总结</p>
      </div>
      <div class="card">
        <div class="card-icon">🔧</div>
        <h3>项目实践</h3>
        <p>整理和展示各类实战项目，包括前端、后端、DevOps 等技术栈</p>
      </div>
      <div class="card">
        <div class="card-icon">📚</div>
        <h3>学习笔记</h3>
        <p>沉淀知识，整理学习过程中的关键知识点和踩坑记录</p>
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
        <div class="post-image">📄</div>
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

<section class="features">
  <div class="container">
    <h2 class="section-title">快速链接</h2>
    <div class="cards">
      <div class="card">
        <div class="card-icon">📁</div>
        <h3>GitHub</h3>
        <p>查看我的开源项目和代码仓库</p>
        <a href="https://github.com/{{ site.github_username }}" class="read-more" target="_blank">访问 →</a>
      </div>
      <div class="card">
        <div class="card-icon">📧</div>
        <h3>联系我</h3>
        <p>欢迎交流技术问题和合作机会</p>
        <a href="mailto:your-email@example.com" class="read-more">发送邮件 →</a>
      </div>
      <div class="card">
        <div class="card-icon">🔗</div>
        <h3>关于本站</h3>
        <p>了解这个博客的创建背景和技术栈</p>
        <a href="/about/" class="read-more">了解更多 →</a>
      </div>
    </div>
  </div>
</section>