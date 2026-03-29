---
layout: default
title: 首页
---

{% assign new_post_url = site.github.repository_url | append: '/new/main/thoughts' %}

<section class="hero-card">
  <p class="eyebrow">JBook</p>
  <h1>把每天值得留下来的东西，像便签一样发布出去。</h1>
  <p class="hero-lead">这是一个基于 Jekyll 的移动端优先博客模板。平时只要在 <code>thoughts/</code> 里新建 Markdown 文件，推送后就会自动生成站点页面，并带有 PWA 安装与离线缓存能力。</p>
  <div class="hero-actions">
    <a class="primary-action" href="{{ new_post_url }}" target="_blank" rel="noreferrer">新建一篇</a>
    <a class="secondary-action" href="{{ '/about' | relative_url }}">查看说明</a>
  </div>
</section>

<section class="section-head">
  <div>
    <p class="eyebrow">Latest Notes</p>
    <h2>最近的记录</h2>
  </div>
  <p class="section-note">共 {{ site.posts | size }} 篇</p>
</section>

<ul class="post-grid">
{% for post in site.posts %}
  {% assign preview = post.content | strip_html | strip_newlines | strip | truncate: 96 %}
  <li class="post-card">
    <a class="post-card-link" href="{{ post.url | relative_url }}">
      <div class="post-card-meta">
        <span>{{ post.date | date: "%Y-%m-%d" }}</span>
        <span>随记</span>
      </div>
      <h3>{{ post.title }}</h3>
      <p>{% if preview == "" %}这篇记录很短，打开看完整内容。{% else %}{{ preview }}{% endif %}</p>
      <span class="post-card-more">继续阅读</span>
    </a>
  </li>
{% endfor %}
</ul>
