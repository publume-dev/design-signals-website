---
decisionKey: "3f30ca208f5739b86da83e328bb931595681b9e51be967c0169dd0aa2436337a"
language: "en"
title: "Garden Anomaly: WebGPU Glass with TSL Displacement, CPU Physics, and Procedural Audio"
summary: "Garden Anomaly is a tiny Codrops experiment that renders a deformable transmissive glass shell with Three.js WebGPURenderer and TSL node materials while bubbles are simulated on the CPU and tones are generated with the Web Audio API. The writeup offers front-end developers a compact working example of custom vertex displacement, Position Based Dynamics, and procedural audio in a WebGPU scene."
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

The whole scene is rendered with WebGPURenderer using TSL node materials. The glass shell uses a MeshPhysicalNodeMaterial with transmission, thickness, IOR, iridescence, clearcoat, and blue attenuation color; impact bulges are driven by a custom TSL positionNode whose vertex displacement reads an 8-slot uniform array of direction and amplitude vectors.

For developers building interactive WebGPU scenes, the bubble simulation is a CPU-based Position Based Dynamics system using semi-implicit Euler integration, constraint iterations, and mass-weighted collisions, so the approach works without a GPU compute pass. Sound is generated procedurally with the Web Audio API: tones are triggered only when a bubble hits the glass hard enough to create a bulge, using a pentatonic scale and oscillator stacks. The bubbles are kept opaque because the transmission pass currently ignores transparent geometry, and the AudioContext is created and resumed on the first pointer interaction to comply with browser autoplay policies.
