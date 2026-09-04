---
decisionKey: "4ec299f88fba857f68808cd56b0c7d8eb9ee98a271f8d1ef896a28d2dc5fb8ed"
language: "zh-CN"
title: "从射线到网格：用 vgpu 构建 Vercel 的 Prism"
summary: "Vercel 的 vgpu 库发布页面中的 Prism 视觉效果最初采用耗时的反向射线追踪，后来改用 3D 网格方法，既更平滑又更便宜。该着色器还包含自适应质量系统，可根据 GPU 性能、电池电量和帧率稳定性动态调整。"
publishedAt: "2026-09-04T12:17:13.130Z"
score: 0.9
topics:
  - "WebGPU"
  - "Shader Development"
  - "Performance Optimization"
  - "3D Graphics"
topicIds:
  - "webgpu-1sv4mwp"
  - "shader-development-kixkwp"
  - "performance-optimization-30t7f2"
  - "3d-graphics-2b3t1f"
sourceUrls:
  - "https://tympanus.net/codrops/2026/09/03/from-rays-to-meshes-building-vercels-prism-with-vgpu/"
---

Vercel 的 vgpu 库发布页面中的 Prism 视觉效果最初采用每像素 16 个采样点的反向射线追踪，每帧进行抖动并随时间累积，这种方法既昂贵又不够锐利。开发者随后用 3D 网格方法替代了射线追踪：连接相邻的波长路径形成三角形面，从而使效果更平滑且成本更低。

这一改动直接影响 WebGPU 图形应用的开发者，他们可以在追求高质量视觉效果的同时控制性能成本。此外，着色器中内置的自适应质量系统会根据三个信号自动降低质量：GPU 等级（低端或移动设备默认低质量）、电池电量（低于 30% 且未充电时）以及帧率不稳定。这为在多样设备上运行 WebGPU 应用提供了实际的性能优化模式。

玻璃着色器使用立方体贴图环境映射来模拟反射，这一技术改编自早期 eve.dev 的视觉效果。对于浅色模式，开发者通过 AI 生成的概念图反向工作，组合了阴影纹理、用于墙面凹凸的法线贴图以及 AI 生成的叠加层来模拟光照。
