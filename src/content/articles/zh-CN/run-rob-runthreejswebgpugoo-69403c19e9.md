---
decisionKey: "69403c19e900ce4c37b1479741d1cc0dfb5c7345e30a08d151047844ca25fefd"
language: "zh-CN"
title: "Run Rob Run：使用Three.js和WebGPU构建音乐反应式Goo"
summary: "本文详细介绍了如何用Three.js和WebGPU构建一个音乐反应式的3D goo效果，包括分层网格、滚动变形和音频响应等技术细节，为设计者和开发者提供了可实践的技巧。"
publishedAt: "2026-08-20T14:10:27.715Z"
score: 0.87
topics:
  - "Three.js WebGPU"
  - "Music-Reactive 3D"
  - "Creative Development"
  - "Performance Optimization"
topicIds:
  - "three-js-webgpu-1k4ezco"
  - "music-reactive-3d-aalv03"
  - "creative-development-1rswwt5"
  - "performance-optimization-30t7f2"
sourceUrls:
  - "https://tympanus.net/codrops/2026/08/20/run-rob-run-building-a-music-reactive-goo-with-three-js-and-webgpu/"
---

该goo效果由多个网格层叠加而成，包括外部折射外壳、橙色核心和薄外层，每层使用不同的材质和响应参数。滚动变形通过结合方向噪声和将顶点拉向最近立方体面的立方体投影，在有机形体和立方体之间平滑过渡。

音乐反应强调低频的鼓点和拍手声，同时抑制高频瞬态以减少杂乱运动。系统采用非对称的起音和释放阻尼，起音更快而释放更慢，从而使goo具有物理重量感。

性能优化包括预计算噪声纹理、交错更新法线，以及滚动时禁用悬停效果。这些措施有助于在保持视觉质量的同时提升运行性能。
