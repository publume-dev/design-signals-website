---
decisionKey: "f4d8a37ff1d0d7ec19017cfeb016516f3044955697f8ef3b8973253cbb609ecd"
language: "en"
title: "Beyond the Luminance Ramp: A Shape-Aware ASCII Renderer in Three.js"
summary: "A novel ASCII renderer in Three.js compares a shape vector from each character cell against all 95 printable ASCII characters, enabling diagonal edges to be represented by characters that follow the edge rather than noise."
publishedAt: "2026-09-05T12:15:11.941Z"
score: 0.85
topics:
  - "ASCII Rendering"
  - "Three.js"
  - "Creative Coding"
  - "Shader Techniques"
topicIds:
  - "ascii-rendering-k0z888"
  - "three-js-1dn7yho"
  - "creative-coding-1a5pw9i"
  - "shader-techniques-18oog7b"
sourceUrls:
  - "https://tympanus.net/codrops/2026/09/04/beyond-the-luminance-ramp-a-shape-aware-ascii-renderer-in-three-js/"
---

A shape-aware ASCII renderer in Three.js samples six inner points and ten outer taps per character cell, builds a six-value shape vector, and selects the nearest matching glyph from all 95 printable ASCII characters, enabling diagonal edges to be represented by characters that follow the edge rather than noise.

The renderer runs three passes per frame: a scene pass, a cell pass that selects glyph indices, and a post pass that stamps glyphs from an atlas, which keeps the glyph search cost at once per 6x10 pixel cell.

The glyph atlas is rasterized at runtime from the resolved monospace font, with 8 pixels of bleed around each cell to prevent clipping, and uses a size formula that fits both tall and wide glyphs without per-glyph measurement.

The cell shader applies directional contrast enhancement by comparing each inner sample against the brightest neighbouring sample outside the cell, widening the gap between the dim and bright sides of an edge and enabling correct glyph selection at boundaries.
