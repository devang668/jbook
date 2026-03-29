---
layout: default
title: 关于
---

{% assign new_post_url = site.github.repository_url | append: '/new/main/thoughts' %}

<section class="info-card">
  <p class="eyebrow">About</p>
  <h1>这是一个尽量不打断写作的博客模板。</h1>
  <p>你只需要在 <code>thoughts/</code> 里新建一个 Markdown 文件，第一行写标题，下面直接写正文，推送后站点就会自动更新。</p>
  <p>模板内置了 GitHub Pages 工作流、Cloudflare Pages 兼容配置、PWA 安装能力和适合手机阅读的界面。</p>
  <div class="info-actions">
    <a class="primary-action" href="{{ new_post_url }}" target="_blank" rel="noreferrer">开始写作</a>
    <a class="secondary-action" href="{{ site.github.repository_url }}" target="_blank" rel="noreferrer">查看仓库</a>
  </div>
</section>
