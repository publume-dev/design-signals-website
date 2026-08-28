---
decisionKey: "aaeabe3bd63a30074e7c9327eac54685549595d2f3d495f21448d97a37a76975"
language: "zh-CN"
title: "Goodgrowth 作品集：启动序列、旋转光盘与作品集的艺术"
summary: "Goodgrowth 的作品集网站使用 Three.js 和 GSAP 实现 3D 元素与动画，并通过多项细节优化（如将主 CD 模型从 9.7MB 减至 182KB）提升性能。"
publishedAt: "2026-08-28T21:50:05.698Z"
score: 0.85
topics:
  - "Creative Development"
  - "Three.js"
  - "GSAP"
  - "WebGL"
  - "Portfolio Design"
topicIds:
  - "creative-development-1rswwt5"
  - "three-js-1dn7yho"
  - "gsap-ai8j4e"
  - "webgl-cu9x0q"
  - "portfolio-design-pqe443"
sourceUrls:
  - "https://tympanus.net/codrops/2026/08/27/goodgrowth-boot-sequences-spinning-discs-and-the-art-of-the-portfolio/"
---

Goodgrowth 的作品集网站采用 Three.js 处理 3D 元素，GSAP 负责动画，Lenis 实现平滑滚动，Vite 构建，并使用原生 JavaScript 与 ES 模块。

这个案例对设计者和开发者有直接影响：缩略图以 0.09 秒的间隔产生螺旋尾迹效果，地球仪使用正交视图保持经线精确，自旋比例从 0.6 调整为 0.571 以确保静止姿态一致，CD 着色器通过扫描项使蝴蝶结图案随视角变化而非几何旋转。

在优化方面，移除未使用的 PBR 贴图并进行焊接与量化处理后，主 CD GLB 文件从 9.7MB 减少到 182KB，且视觉上无差异。
