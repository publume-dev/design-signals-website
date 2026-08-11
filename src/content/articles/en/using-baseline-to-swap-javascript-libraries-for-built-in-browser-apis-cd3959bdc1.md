---
decisionKey: "cd3959bdc1a62b7b73f3d44a32e6a7abf6272f6d59ee01a802973c3fd78461bd"
language: "en"
title: "Using Baseline to Swap JavaScript Libraries for Built-In Browser APIs"
summary: "Baseline, the WebDX Community Group's compatibility classification, gives front-end teams a practical signal for replacing bundled JavaScript libraries with native browser APIs. The approach can reduce shipped script while preserving behavior, with swaps such as relative-time formatting and dialogs already in the Widely available tier."
publishedAt: "2026-08-11T18:44:51.310Z"
score: 0.88
topics:
  - "Web Development"
  - "Front-End Performance"
  - "JavaScript"
topicIds:
  - "web-development-znmevs"
  - "front-end-performance-g6duua"
  - "javascript-zxjsqy"
sourceUrls:
  - "https://smashingmagazine.com/2026/08/how-baseline-can-help-ship-less-javascript/"
---

The WebDX Community Group's Baseline project labels web platform features as Limited, Newly available, or Widely available, and Smashing Magazine argues those labels are a practical guide for auditing dependencies. For example, Intl.RelativeTimeFormat is Widely available and can stand in for libraries like timeago.js, while the dialog element's Widely available support brings built-in focus trapping, Escape-to-close behavior, and top-layer rendering.

Applied to common HTTP and formatting libraries, the swap changes what ships to the browser. Replacing axios with a thin fetch wrapper saves about 17 KB gzipped, though the wrapper must check res.ok because fetch resolves on HTTP errors rather than rejecting the way axios does. Intl.DurationFormat is Baseline Newly available, having shipped in all major engines in March 2025.

The article treats typical dependency savings of 60–90 KB as an observation rather than a measured result, so those numbers should not be read as a formal benchmark. The source also ends inside the UI Primitives section, leaving body-scroll-lock and anchor positioning tradeoffs out of this summary.
