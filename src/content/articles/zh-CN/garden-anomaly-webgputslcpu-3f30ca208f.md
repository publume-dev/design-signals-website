---
decisionKey: "3f30ca208f5739b86da83e328bb931595681b9e51be967c0169dd0aa2436337a"
language: "zh-CN"
title: "Garden Anomaly：一个基于 WebGPU、TSL、CPU 物理与程序化音频的小型实验"
summary: "Codrops 发布的 Garden Anomaly 展示了如何用 WebGPURenderer 与 TSL 节点材质渲染可变形玻璃外壳，同时在 CPU 上用 Position Based Dynamics 驱动气泡，并通过 Web Audio 生成五声音阶音效。该实验为前端开发者提供了一套可借鉴的小型实时图形与交互音频实现。"
publishedAt: "2026-08-11T11:13:09.038Z"
score: 0.85
topics:
  - "WebGPU"
  - "Three.js"
  - "Creative Coding"
  - "Front-end Craft"
topicIds:
  - "webgpu-1sv4mwp"
  - "three-js-1dn7yho"
  - "creative-coding-1a5pw9i"
  - "front-end-craft-1op2an2"
sourceUrls:
  - "https://tympanus.net/codrops/2026/08/06/garden-anomaly-a-tiny-webgpu-and-tsl-experiment/"
---

该场景全程使用 WebGPURenderer 和 TSL 节点材质。玻璃外壳采用 MeshPhysicalNodeMaterial，配置了 transmission、thickness、IOR、iridescence、clearcoat 和蓝色衰减色；气泡撞击产生的凸起则由自定义 TSL positionNode 实现，通过一个包含方向与振幅向量的 8 槽 uniform 数组对顶点进行位移。

对于构建交互式 WebGPU 场景的开发者，这套物理方案在 CPU 上运行，采用半隐式欧拉积分、约束迭代和基于质量的碰撞，因此不依赖 GPU compute 也能获得可预测的交互效果。声音通过 Web Audio API 程序化生成，只有当气泡撞击玻璃的力度足以产生凸起时才会触发，并使用五声音阶和振荡器堆叠。由于 transmission pass 目前会忽略透明几何体，气泡保持不透明；AudioContext 则会在首次指针交互时创建并恢复，以符合浏览器自动播放策略。
