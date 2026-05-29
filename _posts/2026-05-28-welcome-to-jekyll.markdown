---
layout: post
title: "Jekyll + GitHub Pages 快速搭建个人博客"
date: 2026-05-28
categories: Jekyll GitHub
---

## 为什么选择 Jekyll？

Jekyll 是一个静态网站生成器，特别适合搭建个人博客和文档网站。结合 GitHub Pages 可以免费托管网站，而且不需要管理服务器。

### Jekyll 的优势

1. **简单易用** - 纯文本文件管理，无需数据库
2. **免费托管** - GitHub Pages 免费提供托管服务
3. **版本控制** - 所有内容都在 Git 中管理
4. **自定义性强** - 完全掌控网站代码和样式
5. **静态网站** - 加载速度快，SEO 友好

## 快速开始

### 环境要求

- Ruby (>= 2.5)
- RubyGems
- GCC / Make

### 安装步骤

```bash
# 1. 安装 Jekyll 和 Bundler
gem install jekyll bundler

# 2. 创建新站点
jekyll new my-blog

# 3. 进入目录
cd my-blog

# 4. 启动开发服务器
bundle exec jekyll serve

# 5. 访问 http://localhost:4000
```

### 项目结构

```
my-blog/
├── _posts/          # 博客文章目录
│   └── 2024-01-01-hello-world.markdown
├── _layouts/        # 布局模板
├── _includes/       # 可复用组件
├── _config.yml      # 配置文件
├── assets/          # 静态资源
└── index.markdown   # 首页
```

## Jekyll 核心概念

### Front Matter

每个 Markdown 文件顶部需要添加 YAML front matter：

```yaml
---
layout: post
title: "我的文章标题"
date: 2024-01-01
categories: 技术
---
```

### Liquid 模板语言

Jekyll 使用 Liquid 模板语言处理动态内容：

```liquid
{% for post in site.posts %}
  <h2>{{ post.title }}</h2>
  <p>{{ post.date | date: "%Y-%m-%d" }}</p>
{% endfor %}
```

### Markdown 支持

Jekyll 自动将 Markdown 转换为 HTML：

```markdown
## 二级标题

- 列表项1
- 列表项2

**粗体** 和 *斜体*
```

## 部署到 GitHub Pages

### 方式一：直接推送源码

1. 创建 `username.github.io` 仓库
2. 推送 Jekyll 项目代码
3. GitHub Pages 自动构建发布

### 方式二：使用 GitHub Actions

创建 `.github/workflows/deploy.yml`：

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Setup Ruby
        uses: ruby/setup-ruby@v1

      - name: Install dependencies
        run: bundle install

      - name: Build site
        run: bundle exec jekyll build

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./_site
```

## 常用插件

在 `_config.yml` 中配置插件：

```yaml
plugins:
  - jekyll-feed
  - jekyll-seo-tag
  - jekyll-sitemap
```

## 总结

Jekyll + GitHub Pages 是搭建个人博客的绝佳组合，简单、高效、免费。希望这篇文章对你有帮助！

如有问题，欢迎在评论区留言交流！