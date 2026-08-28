---
decisionKey: "aaeabe3bd63a30074e7c9327eac54685549595d2f3d495f21448d97a37a76975"
language: "en"
title: "Goodgrowth: Boot Sequences, Spinning Discs, and the Art of the Portfolio"
summary: "The Goodgrowth portfolio site uses Three.js and GSAP for 3D and animation, with detailed optimizations like reducing the main CD model from 9.7MB to 182KB."
publishedAt: "2026-08-28T21:50:05.698Z"
score: 0.85
topics:
  - "Creative Development"
  - "Three.js"
  - "GSAP"
  - "WebGL"
  - "Portfolio Design"
topicIds:
  - "creative-development-1rswwt5"
  - "three-js-1dn7yho"
  - "gsap-ai8j4e"
  - "webgl-cu9x0q"
  - "portfolio-design-pqe443"
sourceUrls:
  - "https://tympanus.net/codrops/2026/08/27/goodgrowth-boot-sequences-spinning-discs-and-the-art-of-the-portfolio/"
---

The Goodgrowth portfolio site leverages Three.js for 3D elements, GSAP for animation, Lenis for smooth scroll, Vite for build, and vanilla JS with ES modules.

The implementation details matter for designers and developers: thumbnails spiral with a 0.09s stagger for a trailing effect, the globe uses an orthographic view to keep meridian curves exact, the spin ratio snapped to 0.571 ensures consistent rest poses, and the CD shader uses a sweep term so the bow-tie pattern pivots with viewing angle.

Stripping unused PBR maps and welding plus quantization reduced the main CD GLB from 9.7MB to 182KB without visual difference.
