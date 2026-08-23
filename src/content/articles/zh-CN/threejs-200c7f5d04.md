---
decisionKey: "200c7f5d04f075aad8cff04c5a39750fd79144dcb2bf00bbfb1744f73d3c510d"
language: "zh-CN"
title: "Three.js 性能优化：从像素预算到合成器陷阱的实战记录"
summary: "本文通过 FRONTIER 和 LXSTNGHT 两个项目，总结了多个 Three.js 性能优化技巧，包括像素预算、着色器合并、光照处理与后期合成器的常见陷阱。这些经验可帮助开发者避免常见的性能瓶颈。"
publishedAt: "2026-08-23T13:46:34.704Z"
score: 0.9
topics:
  - "WebGL Performance"
  - "Three.js"
  - "React Three Fiber"
  - "Shader Optimization"
  - "Case Study"
topicIds:
  - "webgl-performance-pbfq54"
  - "three-js-1dn7yho"
  - "react-three-fiber-504eqm"
  - "shader-optimization-1rfw0xh"
  - "case-study-1yqqfgc"
sourceUrls:
  - "https://tympanus.net/codrops/2026/08/22/sixty-frames-for-the-record-a-three-js-game-seven-fly-throughs-and-a-wall-of-crts/"
---

在 FRONTIER 项目中，将绘图缓冲限制为绝对像素预算而非固定 devicePixelRatio，填充成本降低一半且视觉效果无明显差异。

全屏 DOM 叠加层配合 mix-blend-mode 在 WebGL 画布上导致每帧 30-45 毫秒的合成开销；改用渲染管线中的融合着色器效果后消除了卡顿。此外，切换点光源可见性会导致着色器程序重编译，因为光源数量在编译时固定，将强度设为 0 可避免重编译。

在 LXSTNGHT 系列中，将数百个几何体合并为单个网格将绘制调用从 1421 次减少到 25 次，但禁用了视锥剔除；按材质和 z 段重新合并后恢复了剔除，提交的三角形数量根据相机位置减少了 21-37%。

EffectComposer 默认使用 8 位帧缓冲，会钳制 HDR 发光值导致高光过曝；设置为 HalfFloatType 可保留 HDR 范围。Bloom 的默认混合函数为 SCREEN，当场景和发光值都超过 1.0 时可能产生负值，导致明亮发光物体周围出现黑色光晕；使用加法混合函数可防止此反转。
