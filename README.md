# 架构与认知

> AI 时代全栈工程师关于架构与认知的零碎思考。

个人博客，基于 [Astro Paper](https://github.com/satnaing/astro-paper) 主题。

## 技术栈

- **框架**: [Astro](https://astro.build/) 7
- **主题**: [Astro Paper](https://github.com/satnaing/astro-paper) v6.1.0
- **样式**: Tailwind CSS 4
- **内容**: MDX（src/content/posts/）
- **搜索**: Pagefind（构建时生成）
- **部署**: Cloudflare Pages
- **包管理**: pnpm

## 本地开发

```bash
pnpm install      # 安装依赖
pnpm dev          # 启动 dev server (http://localhost:4321)
pnpm build        # 生产构建 + Pagefind 索引
pnpm preview      # 预览构建产物
pnpm lint         # ESLint
pnpm format       # Prettier
```

## 内容写作

文章放在 `src/content/posts/` 下，每个文件一篇 MDX。

frontmatter 字段：

```yaml
---
author: Sunny Zeng           # 默认从 config 读
pubDatetime: 2026-07-20T08:00:00.000Z
title: "文章标题"
featured: false               # 是否显示在首页"精选"区
draft: true                   # 草稿状态：true = 不发布、不索引
tags: ["架构", "AI"]
description: "一句话描述（用于 SEO meta 和 RSS）"
modDatetime: 2026-07-21T00:00:00.000Z  # 可选：最后修改时间
ogImage: ./og.png             # 可选：自定义 OG 图
canonicalURL: https://...     # 可选：原文地址
---
```

## 目录结构

```
src/
├── content/
│   ├── pages/         # 静态页面（about 等）
│   └── posts/         # 博客文章（MDX）
├── layouts/           # 页面布局
├── pages/             # 路由
├── components/        # 复用组件
├── i18n/
│   └── lang/          # UI 字符串（多语言）
├── config.ts          # 解析后的站点配置
├── astro-paper.config.ts  # 站点元数据
└── styles/            # 全局样式
```

## 写作约定

- **节奏**: 每周一篇，周中发布
- **长度**: 长文为主（> 1000 字）
- **角度**: AI 时代全栈工程师的架构与认知
- **编辑**: 每篇至少经历一次隔天重读
- **草稿**: 用 `draft: true` 标记，构建时自动排除

## 部署

推送 `main` 分支 → Cloudflare Pages 自动构建 → `https://<domain>/` 上线。

构建配置：

- Build command: `pnpm build`
- Output directory: `dist`
- Environment: `NODE_VERSION=24`

## 许可

内容采用 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) 许可。

代码部分遵循上游 [Astro Paper](https://github.com/satnaing/astro-paper) 的 MIT 许可。
