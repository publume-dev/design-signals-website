---
decisionKey: "69403c19e900ce4c37b1479741d1cc0dfb5c7345e30a08d151047844ca25fefd"
language: "en"
title: "Run Rob Run: Building a Music-Reactive Goo with Three.js and WebGPU"
summary: "This article details creating a music-reactive 3D goo with Three.js and WebGPU, covering layered meshes, scroll morphing, and audio response techniques that designers and developers can apply."
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

The goo is built from layered meshes: an outer refractive shell, an orange core, and a thin outer coat, each using different materials and response settings. Scroll morph blends between an organic blob and a cube by mixing direction-based noise with a cube projection that pulls vertices toward the nearest cube face.

The music reaction emphasizes low-frequency kicks and claps while dampening high-frequency transients to avoid noisy movement. The system applies asymmetric attack and release damping to give the goo physical weight, with faster attack and slower release.

Performance optimizations include precomputing noise textures, staggering normal updates, and disabling hover effects during scroll. These measures help maintain visual quality while improving runtime performance.
