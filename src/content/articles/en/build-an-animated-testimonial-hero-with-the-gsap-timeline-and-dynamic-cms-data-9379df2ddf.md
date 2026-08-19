---
decisionKey: "9379df2ddff23080742871e26ccba2487d852032891e299423f55130e987c3c1"
language: "en"
title: "Build an Animated Testimonial Hero with the GSAP Timeline and Dynamic CMS Data"
summary: "A tutorial demonstrates how to build an animated testimonial hero using GSAP timelines with Webflow CMS data, including counter animations, collage layouts without custom code, and container-query-based scaling."
publishedAt: "2026-08-19T03:13:48.117Z"
score: 0.85
topics:
  - "Webflow CMS Animation"
  - "GSAP Timeline"
  - "CSS Container Queries"
  - "Front-End Craft"
  - "Design Systems"
topicIds:
  - "webflow-cms-animation-1ubcxki"
  - "gsap-timeline-1w1j5s1"
  - "css-container-queries-5uv1ab"
  - "front-end-craft-1op2an2"
  - "design-systems-1cjwd7p"
sourceUrls:
  - "https://tympanus.net/codrops/2026/08/18/building-an-animated-testimonial-hero-using-the-gsap-timeline-and-dynamic-cms-data/"
---

The counter animation in this implementation is not a numeric count-up but a vertical strip of digits sliding via `transform: translateY`, with easing controlled by an ease-out function and adjustable revolutions and duration.

Developers can achieve a collage layout in Webflow without writing custom code by using `:first-child`, `:nth-child(even)`, and `:last-child` selectors to style individual CMS collection items. Additionally, setting `container-type: inline-size` and `font-size: 1cqw` on a wrapper allows em-based sizing to scale all items proportionally with the container width.

The tutorial also shows how to use Webflow's visual timeline to build a looping GSAP animation with 3D effects by setting perspective, rotateX, scale, opacity, and stagger directly in the UI, eliminating the need for custom code.
