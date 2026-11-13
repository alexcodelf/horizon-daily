---
layout: default
title: Home
---

# Horizon Daily

每日由 [Horizon](https://github.com/Thysrael/Horizon) 自动生成，AI 筛选与摘要。

---

## 中文速递 <a class="rss-icon" href="{{ '/feed-zh.xml' | relative_url }}" aria-label="订阅中文">RSS</a>

<ul>
  {% assign zh_posts = site.posts | where: "lang", "zh" %}
  {% for post in zh_posts limit:20 %}
    <li><a href="{{ post.url | relative_url }}">{{ post.date | date: "%Y-%m-%d" }}</a></li>
  {% else %}
    <li><em>暂无内容</em></li>
  {% endfor %}
</ul>

## English Digest <a class="rss-icon" href="{{ '/feed-en.xml' | relative_url }}" aria-label="Subscribe English">RSS</a>

<ul>
  {% assign en_posts = site.posts | where: "lang", "en" %}
  {% for post in en_posts limit:20 %}
    <li><a href="{{ post.url | relative_url }}">{{ post.date | date: "%Y-%m-%d" }}</a></li>
  {% else %}
    <li><em>No posts yet</em></li>
  {% endfor %}
</ul>
