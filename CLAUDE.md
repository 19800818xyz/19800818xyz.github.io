# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 常用命令

```bash
# 本地实时预览（含草稿）
hugo server -D

# 新建文章（用 archetypes/post.md 模板）
hugo new post/<文章slug>/index.md

# 生产构建
hugo --gc --minify
```

部署由 `.github/workflows/hugo.yml` 自动处理：push 到 `main` 分支后，GitHub Actions 构建并发布到 GitHub Pages（`https://19800818xyz.github.io`）。Hugo 版本固定为 `0.160.0 extended`。

## 架构概览

- **框架**：Hugo + [`hugo-theme-stack`](https://stack.jimmycai.com/config/)（以 git submodule 方式挂载于 `themes/hugo-theme-stack/`）
- **内容格式**：Page Bundle — 每篇文章一个文件夹，结构为 `content/post/<slug>/index.md`，封面图和附图放同目录
- **主配置**：`hugo.toml`，包含菜单、评论、配色、数学公式等全局设置

## 文章 Front Matter

```yaml
---
title: "标题"
description: "摘要，显示在列表卡片上"
slug: "url-slug"
date: 2026-05-03T10:00:00+08:00
lastmod: 2026-05-03T10:00:00+08:00
draft: false
categories:
  - 分类名
tags:
  - 标签1
math: false          # 需要 KaTeX 公式时改为 true
# image: "cover.jpg" # 封面图，放同目录下
---
```

`draft: true` 的文章只在 `hugo server -D` 时显示，不会被构建发布。

## 自定义扩展

| 路径 | 作用 |
|------|------|
| `assets/scss/custom.scss` | 毛玻璃侧边栏、卡片悬停动效、标签云配色；主题 accent color 为 `#6366f1` |
| `layouts/_default/_markup/render-codeblock-mermaid.html` | 支持 Mermaid 流程图 |
| `layouts/partials/footer/custom.html` | 自定义页脚 |

## 评论系统

使用 Giscus（基于 GitHub Discussions）。`hugo.toml` 中 `repoID` 和 `categoryID` 目前为占位符，需到 [giscus.app](https://giscus.app) 生成后填入。
