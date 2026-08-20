---
decisionKey: "ee61ecd19282a6b23e965bb4a3c93ce172fc3946edacc871d7d187ec44efe37a"
language: "zh-CN"
title: "利用深度图和Three.js实现图像重光照"
summary: "本文介绍了一种使用深度图、Three.js、TSL和WebGPU对二维图像进行重光照的技术，该方法能模拟三维表面在不同光源下的反应。"
publishedAt: "2026-08-20T14:10:27.715Z"
score: 0.85
topics:
  - "Three.js"
  - "WebGPU"
  - "Depth Maps"
  - "Image Effects"
  - "TSL"
topicIds:
  - "three-js-1dn7yho"
  - "webgpu-1sv4mwp"
  - "depth-maps-1q87g29"
  - "image-effects-czh5ao"
  - "tsl-1fwwjdg"
sourceUrls:
  - "https://tympanus.net/codrops/2026/08/19/relighting-images-with-depth-maps-and-three-js/"
---

通过深度估计模型（如Depth Anything 3）或提供的深度生成工具，可以从二维图像生成深度图。

将深度图转换为浮点值并进行模糊处理，可以消除8位量化阶梯，从而提升光照质量；由深度图导出的法线贴图能使光照反应出三维表面效果；添加来自照片亮度的细节渐变可增强移动光源下的表面细节感知；阴影通过从每个像素向光源方向追踪线段并累积遮挡来模拟。

MeshPhongNodeMaterial可以组合颜色、法线和环境光遮蔽节点来实现重光照效果。
