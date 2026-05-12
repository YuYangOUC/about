---
title: GitHub Pages 踩坑小记
date: 2026-05-12 22:30:00 +0800
categories: [技术笔记, DevOps]
tags: [github, pages, jekyll]
---

把博客搭在 GitHub Pages 上的过程中踩了几个坑，记一下给以后的自己。

## 仓库命名决定 URL 形态

- `<username>.github.io` → 访问地址是 `https://<username>.github.io`
- 任意其它名字 → 访问地址是 `https://<username>.github.io/<repo-name>`

**重命名仓库**会让 URL 跟着变（配置自动迁移），**但 Unpublish 会清空 Pages 配置**，需要重新 Save。

## 子路径下 baseurl 的坑

项目仓库部署在子路径下（`/blog`、`/about2` 之类），如果 `_config.yml` 里的 `baseurl` 没设对，所有静态资源会 404。

好消息是：用 GitHub Actions + `actions/configure-pages@v5` 的话，它会**自动填入 baseurl**，`_config.yml` 里保留空字符串反而最稳。

## Chirpy 必须用 Actions 构建

Chirpy 依赖的 gem 不在 GitHub Pages 默认白名单里，用 `Deploy from a branch` 会报错。

解决：

1. Settings → Pages
2. Source 选 **GitHub Actions**（不是 Deploy from a branch）
3. 推送后 Actions 自动构建

Starter 模板里已经带了 `.github/workflows/pages-deploy.yml`，开箱即用。

## 浏览器缓存会骗你

改完仓库名或 Pages 配置后，旧 URL 看起来"还能访问"——十有八九是浏览器缓存。

验证真实状态：

```bash
curl -I https://yuyangouc.github.io/some-path/
```

返回 404 就是真的 404，不是你记错了。

---

先这些，遇到新的再补。
