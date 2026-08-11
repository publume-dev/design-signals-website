---
decisionKey: "10f124b10d41d9844cdc47b04832f3a5c03ad561bca2e46f3ec4092614ced372"
language: "zh-CN"
title: "Three.js/WebGPU 程序化笔刷几何：BVH 拾取、弧长重采样与无分配滑块"
summary: "Codrops 的一篇教程展示了如何用 Three.js 与 WebGPU 构建程序化笔刷模式，包括工厂函数、BVH 加速拾取与弧长重采样。这套实现让指针笔迹在移动画布上保持稳定，并让滑块实时调整不产生分配。"
publishedAt: "2026-08-11T18:44:51.310Z"
score: 0.9
topics:
  - "Three.js"
  - "WebGPU"
  - "Procedural Geometry"
topicIds:
  - "three-js-1dn7yho"
  - "webgpu-1sv4mwp"
  - "procedural-geometry-1x08gp6"
sourceUrls:
  - "https://tympanus.net/codrops/2026/08/11/exploring-procedural-geometry-with-three-js-and-webgpu/"
---

该教程将笔刷模式定义为一个工厂函数：它把表面采样转换为 StrokeInstance 对象，因此新增模式无需改动应用绘制代码。由于指针事件按固定频率到达而不是按固定距离，每种模式在生成几何前，都会按固定世界空间步长对原始路径进行累积弧长重采样。

对于正在组装 Three.js 拾取与绘制工具的开发者，这个流程改变了两处常见难点。项目对 three-mesh-bvh 的加速光线投射做了补丁，并启用 firstHitOnly，让 raycaster 在最近三角形处停止，而不是收集并排序所有交点。表面采样也会在拾取瞬间从世界空间转换到锚点的局部空间，并且每次拾取都会重新计算逆矩阵，从而防止画布在两次指针事件之间旋转或移动时，已绘制的几何体滑离表面。

文章还演示了一个为流畅交互设计的实时滑块系统。它会按最大密度/值一次性生成所有实例，并保存稳定的随机排名；applySettings 在原地剔除或重组，所以拖动滑块时不会分配、销毁或重新生成随机值。
