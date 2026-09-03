---
decisionKey: "b7fc1e65a45ccf9f26be18721471a56e6a843000bc6fa7b8fc06bcea5fa637cd"
language: "en"
title: "Building a Real-Time Datamosh Effect with Three.js: Keyframe Suppression and Feedback Loops"
summary: "This article describes a method to achieve a real-time datamosh effect in Three.js by suppressing keyframe refreshes and using a feedback loop, applicable for creative coding and shader effects."
publishedAt: "2026-09-03T12:17:56.661Z"
score: 0.9
topics:
  - "Three.js"
  - "Creative Coding"
  - "Shader Effects"
topicIds:
  - "three-js-1dn7yho"
  - "creative-coding-1a5pw9i"
  - "shader-effects-kdd6tq"
sourceUrls:
  - "https://tympanus.net/codrops/2026/09/02/breaking-the-frame-building-a-real-time-datamosh-effect-with-three-js/"
---

The article presents a concrete method for creating a real-time datamosh effect in Three.js: suppress keyframe refreshes and use a feedback loop with history buffers. Specifically, a fragment shader samples the previous output and mixes it with the current scene render using a motion vector offset.

The implementation requires two history buffers because a shader cannot sample a texture attached to the framebuffer it is drawing into. By rendering the scene with override materials projecting vertices twice—once with current matrices and once with previous frame matrices—the difference in clip space positions divided per-fragment gives screen-space motion vectors.

To create the datamosh effect, the code triggers a scene cut without raising the keyframe flag, causing the decoder to use outdated references while applying vectors from the new scene. The residual correction uses a high-frequency gate that transmits only the detail stronger in the incoming render, making the correction self-limiting.

To reduce blur from repeated resampling, Catmull-Rom interpolation is recommended, and colours are clamped to valid ranges. Additionally, blockiness can be added by sampling motion at block centres, snapping motion to subpixel lattices, and using skip thresholds to create a codec-like appearance.
