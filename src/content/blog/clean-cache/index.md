---
title: 清除 Chrome 缓存
publishDate: 2025-02-13
updatedDate: 2025-02-13
description: 清除 Chrome 缓存，刷新页面。
heroImage: {src : "thumbnail.webp", color: '#718E88' }
category: 'MISCs'
tags:
    - 'Tech Talk'
---

因为在写自己的 Blog 的时候，有的时候会使用自己的图床来加载图片，本身我的图床的搭建可以看 [之前的博客](/blog/imagebed)。其根本的逻辑就是每次上传图片之后，其实就是 push 到了 Github 的 Branch 里面，而使用 Vercel 托管之后，每次 push 都会触发 Vercel 的自动部署，所以每次上传图片之后，都会添加到我的 `pic.axi404.top` 的图片列表中。不过毕竟部署是需要一些时间的，假如再次之前就已经以诸如 Markdown 的语法引用图片，那么就会导致图片无法显示，这很合理。但是问题出现在，即使图片已经部署到了图床中，但是页面就是不显示，这毫无疑问是因为 Chrome 的对这些图片进行了缓存。所以如何清除 Chrome 的缓存呢？

## 方法

本身不是很难，以 Chrome 为例，直接 F12 打开控制台，然后选择停用缓存即可，如下图所示。

![](https://pic.axi404.top/image.5q7jdxkwin.webp)

在这样选择了之后可以刷新页面，这时候就没问题了。

当然还有另一种方法，可以直接清除缓存：

![](https://pic.axi404.top/image.9rjisbt1ix.webp)

希望对你有帮助\~
