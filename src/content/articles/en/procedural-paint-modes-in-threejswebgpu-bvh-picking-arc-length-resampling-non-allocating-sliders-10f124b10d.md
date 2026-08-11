---
decisionKey: "10f124b10d41d9844cdc47b04832f3a5c03ad561bca2e46f3ec4092614ced372"
language: "en"
title: "Procedural Paint Modes in Three.js/WebGPU: BVH Picking, Arc-Length Resampling, Non-Allocating Sliders"
summary: "A Codrops tutorial shows how to build procedural paint modes with Three.js/WebGPU using factory functions, BVH-accelerated picking, and arc-length resampling. The implementation keeps pointer-driven strokes stable on moving canvases and makes live slider edits allocation-free."
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

The tutorial defines a paint mode as a factory function that turns surface samples into StrokeInstance objects, so new modes can be added without changing the application's painting code. Because pointer events arrive at a fixed rate, every mode resamples the raw path by accumulated arc length at a fixed world-space step before building geometry.

For developers assembling Three.js pick-and-paint tools, the pipeline changes two places that usually cause trouble. The project patches three-mesh-bvh's accelerated raycast and enables firstHitOnly, making the raycaster stop at the nearest triangle instead of collecting and sorting all intersections. Surface samples are also converted from world space to the anchor's local space at pick time, and the inverse matrix is recomputed on every pick, which prevents painted geometry from sliding off a canvas that rotates or moves between pointer events.

The same article demonstrates a live slider system built for responsiveness. It generates every instance at maximum density/value once and stores stable random ranks; applySettings culls or recomposes in place, so dragging a slider never allocates, disposes, or re-rolls random values.
