---
decisionKey: "ee61ecd19282a6b23e965bb4a3c93ce172fc3946edacc871d7d187ec44efe37a"
language: "en"
title: "Relighting Images with Depth Maps and Three.js"
summary: "This article presents a technique for relighting 2D images using depth maps, Three.js, TSL, and WebGPU, simulating how a 3D surface reacts to different light sources."
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

A depth map can be generated from a 2D image using a depth estimation model like Depth Anything 3 or a provided depth generation tool.

Converting the depth map to floating-point values and blurring it smooths out 8-bit quantization steps, improving lighting quality. A normal map derived from the depth map allows lighting to react as if the image surface is three-dimensional. Adding detail gradients from the photo's brightness to the normal map enhances perceived surface detail under moving light. Shadows are simulated by tracing a line from each pixel toward the light through the depth map and accumulating occlusion.

MeshPhongNodeMaterial can combine color, normal, and ambient occlusion nodes to create the relighting effect.
