---
title: Fuwari Blog部署
published: 2024-09-19
description: 在本地部署Fuwari Blog
tags: [Blog, Fuwari]
category: Back-end
draft: false
---


项目地址：https://github.com/saicaca/fuwari



先装npm，然后安装gnpm，然后执行`pnpm install` AND `pnpm add sharp`安装依赖

下列指令均需要在项目根目录执行：

|Command|Action|
|:--|:--|
|`pnpm install` 并 `pnpm add sharp`|安装依赖|
|`pnpm dev`|在 `localhost:4321` 启动本地开发服务器|
|`pnpm build`|构建网站至 `./dist/`|
|`pnpm preview`|本地预览已构建的网站|
|`pnpm new-post <filename>`|创建新文章|
|`pnpm astro ...`|执行 `astro add`, `astro check` 等指令|
|`pnpm astro --help`|显示 Astro CLI 帮助|




## ⚙️ 文章头 Frontmatter

```yaml
---
title: My First Blog Post
published: 2023-09-09
description: This is the first post of my new Astro blog.
image: ./cover.jpg
tags: [Foo, Bar]
category: Front-end
draft: false
lang: jp      # 仅当文章语言与 `config.ts` 中的网站语言不同时需要设置
---
```


# 文件位置
1. 通过配置文件 `src/config.ts` 自定义博客
2. 执行 `pnpm new-post <filename>` 创建新文章，并在 `src/content/posts/` 目录中编辑
3. 参考[官方指南](https://docs.astro.build/zh-cn/guides/deploy/)将博客部署至 Vercel, Netlify, GitHub Pages 等；部署前需编辑 `astro.config.mjs` 中的站点设置。