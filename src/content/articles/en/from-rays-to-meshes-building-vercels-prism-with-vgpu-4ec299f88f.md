---
decisionKey: "4ec299f88fba857f68808cd56b0c7d8eb9ee98a271f8d1ef896a28d2dc5fb8ed"
language: "en"
title: "From Rays to Meshes: Building Vercel's Prism with vgpu"
summary: "The Prism visual for Vercel's vgpu library launch initially used costly backward ray casting and was replaced with a 3D mesh approach that is smoother and cheaper. The shader also includes an adaptive quality system that adjusts based on GPU tier, battery level, and frame rate stability."
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

The Prism visual for Vercel's vgpu library launch initially used backward ray casting with 16 samples per pixel, jittered per frame and accumulated over time, which proved expensive and not sharp. The developer replaced ray casting with a 3D mesh approach, connecting neighboring wavelength paths to form triangular faces, resulting in a smoother and cheaper effect.

This change directly affects developers building WebGPU graphics applications who need to balance visual quality with performance costs. Additionally, the shader includes an adaptive quality system that switches to low quality based on three signals: GPU tier (low-tier or mobile starts low), battery level (below 30% and not charging), and frame rate instability. This provides a practical performance optimization pattern for WebGPU apps running on a variety of devices.

The glass shader used a cubemap environment map to fake reflections, adapted from an earlier eve.dev hero. For light mode, the developer worked backward from an AI-generated concept image, composing elements such as a shadow texture, a normal map for wall bumps, and an AI-generated overlay for lighting.
