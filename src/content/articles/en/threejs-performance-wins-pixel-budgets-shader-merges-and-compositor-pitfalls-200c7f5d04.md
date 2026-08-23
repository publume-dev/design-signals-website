---
decisionKey: "200c7f5d04f075aad8cff04c5a39750fd79144dcb2bf00bbfb1744f73d3c510d"
language: "en"
title: "Three.js Performance Wins: Pixel Budgets, Shader Merges, and Compositor Pitfalls"
summary: "This article shares practical Three.js optimization techniques from the FRONTIER and LXSTNGHT projects, covering pixel budgets, shader merging, light handling, and post-processing compositor traps. These insights help developers avoid common performance bottlenecks."
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

In the FRONTIER project, capping the drawing buffer to an absolute pixel budget instead of a fixed devicePixelRatio reduced fill cost by half with no visible output difference.

Using a fullscreen DOM overlay with mix-blend-mode over a WebGL canvas caused 30-45 ms per frame compositing cost; replacing it with a fused shader effect eliminated the hitch. Also, toggling point light visibility triggers shader recompilation because light count is a compile-time constant; setting intensity to 0 avoids this.

In the LXSTNGHT series, merging hundreds of geometries into a single mesh cut draw calls from 1,421 to 25, but disabled frustum culling; re-merging per material and z-segment restored culling and cut submitted triangles by 21-37% depending on camera position.

EffectComposer defaults to an 8-bit frame buffer, clamping HDR emissive values and causing blown-out highlights; setting it to HalfFloatType preserves HDR range. Bloom's default blend function is SCREEN, which can produce negative values when both scene and bloom exceed 1.0, causing black halos; using additive blend prevents this inversion.
