# 🍥Fuwari

基于 [Astro](https://astro.build) 开发的静态博客模板  
基于 [Fuwari](https://fuwari.vercel.app) 改的赤史博客

## ✨ 功能特性

- [x] 基于 Astro 和 Tailwind CSS 开发
- [x] 流畅的动画和页面过渡
- [x] 亮色 / 暗色模式
- [x] 自定义主题色和横幅图片
- [x] 响应式设计
- [x] 评论
- [x] 搜索
- [x] 文内目录
- [x] 友链
- [x] 固定文章
- [x] 烟花爆炸效果（带开关
- [x] 404 页面

## 👀 要求

- Node.js <= 22
- pnpm <= 9

## 🚀 使用方法 1

使用 [create-fuwari](https://github.com/L4Ph/create-fuwari) 在本地初始化项目。

```sh
# npm
npm create fuwari@latest

# yarn
yarn create fuwari

# pnpm
pnpm create fuwari@latest

# bun
bun create fuwari@latest

# deno
deno run -A npm:create-fuwari@latest
```

1. 通过配置文件 `src/config.ts` 自定义博客
2. 执行 `pnpm new-post <filename>` 创建新文章，并在 `src/content/posts/` 目录中编辑
3. 参考[官方指南](https://docs.astro.build/zh-cn/guides/deploy/)将博客部署至 Vercel, Netlify, GitHub Pages 等；部署前需编辑 `astro.config.mjs` 中的站点设置。

## 🚀 使用方法 2

1. 使用此模板[生成新仓库](https://github.com/saicaca/fuwari/generate)或 Fork 此仓库
2. 进行本地开发，Clone 新的仓库，执行 `pnpm install` 和 `pnpm add sharp` 以安装依赖
   - 若未安装 [pnpm](https://pnpm.io)，执行 `npm install -g pnpm`
3. 通过配置文件 `src/config.ts` 自定义博客
4. 通过 `src/content/spec/friends.json` 自定义友链
5. 执行 `pnpm new-post <filename>` 创建新文章，并在 `src/content/posts/` 目录中编辑
6. 参考[官方指南](https://docs.astro.build/zh-cn/guides/deploy/)将博客部署至 Vercel, Netlify, GitHub Pages 等；部署前需编辑 `astro.config.mjs` 中的站点设置。

## ⚙️ 文章 Frontmatter

```yaml
---
title: My First Blog Post
published: 2023-09-09
updated: 2024-11-29
description: This is the first post of my new Astro blog.
image: ./cover.jpg
tags: [Foo, Bar]
category: "Front-end"
draft: false
pinned: false
lang: zh_CN # 仅当文章语言与 `config.ts` 中的网站语言不同时需要设置
---
```

| 字段          | 描述                                                                                 |
| ------------- | ------------------------------------------------------------------------------------ |
| `title`       | 文章标题                                                                             |
| `published`   | 发布日期                                                                             |
| `updated`     | 更新日期                                                                             |
| `description` | 文章描述                                                                             |
| `image`       | 封面图片                                                                             |
| `tags`        | 标签                                                                                 |
| `category`    | 分类                                                                                 |
| `draft`       | 是否为草稿，草稿不会显示                                                             |
| `pinned`      | 设置为 `true` 可将文章固定在博客顶部。固定文章会显示在其他文章之前，不受发布日期影响 |

## 🧞 指令

下列指令均需要在项目根目录执行：

| Command                            | Action                                 |
| :--------------------------------- | :------------------------------------- |
| `pnpm install` 并 `pnpm add sharp` | 安装依赖                               |
| `pnpm dev`                         | 在 `localhost:4321` 启动本地开发服务器 |
| `pnpm build`                       | 构建网站至 `./dist/`                   |
| `pnpm preview`                     | 本地预览已构建的网站                   |
| `pnpm new-post <filename>`         | 创建新文章                             |
| `pnpm astro ...`                   | 执行 `astro add`, `astro check` 等指令 |
| `pnpm astro --help`                | 显示 Astro CLI 帮助                    |
