---
decisionKey: "7850739e6419a52973dec46a8a5e2a0aad09b2599dd954524893e829c143e3f4"
language: "zh-CN"
title: "使用 Three.js 和 GLSL 构建鼠标跟随的方形镜头效果"
summary: "一篇教程展示了如何使用 Three.js 和 GLSL 构建一个鼠标跟随的方形镜头效果，该效果结合了灰度图像、彩色图像和方形遮罩，并应用了镜头畸变和 RGB 偏移。"
publishedAt: "2026-08-25T14:28:54.522Z"
score: 0.9
topics:
  - "WebGL"
  - "Three.js"
  - "GLSL"
  - "Creative Development"
topicIds:
  - "webgl-cu9x0q"
  - "three-js-1dn7yho"
  - "glsl-10yaach"
  - "creative-development-1rswwt5"
sourceUrls:
  - "https://tympanus.net/codrops/2026/08/25/building-a-mouse-following-square-lens-effect-with-three-js-and-glsl/"
---

该教程阐述了一种技术，通过将灰度图像与彩色图像分层，并让一个跟随鼠标的方形遮罩在片段着色器中应用镜头畸变和 RGB 偏移，从而实现鼠标跟随的方形镜头效果。

实现时，将相机 Z 位置设置为函数计算的数值，该数值确保相机的可见高度与网格高度匹配，从而让网格适应视野。为了保持遮罩为方形，无论视口尺寸如何，都将 UV 坐标除以根据网格尺寸导出的宽高比校正因子。此外，通过在片段着色器中将 UV 坐标转换为局部空间，并使用基于畸变强度缩放半径的函数，可将镜头畸变应用于彩色图像。
