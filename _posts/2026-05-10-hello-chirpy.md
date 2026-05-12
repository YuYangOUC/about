---
title: Hello，博客上线
date: 2026-05-10 20:00:00 +0800
categories: [随笔]
tags: [开篇]
pin: true
---

好久没写博客了，今天花了点时间用 **Jekyll + Chirpy** 主题搭了一个，顺便记录一下过程。

## 为什么选 Chirpy

几个理由：

1. **功能齐全** — 侧栏、目录、搜索、分类、tags、归档全都有
2. **暗色主题** — 可以手动切换，深夜友好
3. **GitHub Pages 可部署** — 通过 Actions 自动构建，不用自己管服务器
4. **Markdown 原生** — 发一篇文章 = 新建一个 `.md` 文件

## 目录结构

```
.
├── _config.yml     # 全站配置
├── _posts/         # 博客文章放这里
├── _tabs/          # 顶栏/侧栏页面（about、归档等）
├── assets/         # 自定义图片、图标等
└── index.html      # 首页入口（不用动）
```

## 写作流程

每写一篇新文章：

```bash
cd ~/about
vim _posts/2026-05-12-some-title.md
git add . && git commit -m "post: some title" && git push
```

剩下的交给 GitHub Actions：构建、测试、部署，大约一两分钟后就能看到新文章。

> 后面还会继续折腾主题配色、评论系统、搜索优化等，慢慢来。
{: .prompt-tip }
