---
decisionKey: "dbbad71dc76fc5f78517b965655483ae2214b5d1a506eac13a94775a686a169c"
language: "en"
title: "Building the PX PUSH Website: CRT Effects, Three.js Scenes, and Scroll-Driven Details"
summary: "A Codrops case study documents how the PX PUSH website layers CRT effects, coordinates Three.js scenes, and adds scroll-driven interactions, offering a detailed look at the implementation techniques."
publishedAt: "2026-08-11T11:13:09.038Z"
score: 0.9
topics:
  - "Web Design Case Study"
  - "Three.js Integration"
  - "GSAP Scroll Animations"
  - "Nuxt 3 Development"
topicIds:
  - "web-design-case-study-qhi9rq"
  - "three-js-integration-ev28hi"
  - "gsap-scroll-animations-9t0i1i"
  - "nuxt-3-development-z2mitk"
sourceUrls:
  - "https://tympanus.net/codrops/2026/08/07/the-department-is-open-building-the-px-push-website/"
---

According to the Codrops case study, the site's CRT effect is built from layered fixed overlays: a scanline bar, a repeating line pattern, a backdrop blur bloom, a crt.png vignette, and animated noise. The article also describes three separate Three.js scenes—an extruded chrome logo, a cloud-flight hero, and a floppy disk—coordinated through a pub/sub lifecycle that makes pages wait for all scenes to load before revealing content.

On the About page, scroll velocity drives how the founders are presented: they rotate through 15 photographed angles, with a scroll accumulator switching images like a character-select screen.

The Journal drawer applies a CSS mask for punch holes, maintains its own Lenis instance, and preserves each article's slug, canonical URL, and BlogPosting schema. Marquee titles use a declarative attribute system to attach GSAP timelines for randomized word reveals and blur-fade-outs as sections enter and leave the viewport.

The article does not report performance metrics or user testing for the WebGL effects, so their real-world impact on lower-end devices is not verified.
