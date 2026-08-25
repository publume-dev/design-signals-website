---
decisionKey: "7850739e6419a52973dec46a8a5e2a0aad09b2599dd954524893e829c143e3f4"
language: "en"
title: "Building a Mouse-Following Square Lens Effect with Three.js and GLSL"
summary: "A tutorial demonstrates how to build a mouse-following square lens effect with Three.js and GLSL, combining a grayscale image and a color image with a square mask that applies lens distortion and RGB shift."
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

The tutorial describes a technique for achieving a mouse-following square lens effect by layering a grayscale image and a color image, using a square mask that follows the mouse, and applying lens distortion and RGB shift in the fragment shader.

To implement this, the camera's Z position is set using a function that calculates the distance at which the visible height of the camera matches the mesh height, ensuring the mesh fits within the field of view. To keep the mask square regardless of viewport size, the UV coordinates are divided by an aspect-ratio correction factor derived from the mesh dimensions. Additionally, lens distortion can be applied to the color image by converting UV coordinates to a local space and using a function that scales the radius based on distortion strength.
