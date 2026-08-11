---
decisionKey: "cd3959bdc1a62b7b73f3d44a32e6a7abf6272f6d59ee01a802973c3fd78461bd"
language: "zh-CN"
title: "用 Baseline 判断哪些 JavaScript 依赖可被浏览器原生 API 替换"
summary: "Baseline 是 WebDX Community Group 的兼容性分类体系，它可以帮助前端团队判断哪些 JavaScript 依赖可以被浏览器原生 API 替代。按此思路，团队能在保持功能的同时减少打包体积，例如相对时间格式化和对话框都已进入 Widely available 层级。"
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

WebDX Community Group 的 Baseline 项目把 Web 平台特性分为 Limited、Newly available 和 Widely available 三档；Smashing Magazine 认为这些分类可以作为审查依赖的实用指南。比如 Intl.RelativeTimeFormat 已属于 Widely available，可用于替代 timeago.js 这类相对时间库；dialog 元素同样 Widely available，自带焦点锁定、按 Esc 关闭和 top-layer 渲染。

换用这些内置能力的直接影响是减少实际下发的脚本。用一层薄薄的 fetch 封装替代 axios 可节省约 17 KB gzipped；但要注意 fetch 在 HTTP 错误响应时也会 resolve，需要显式检查 res.ok，而 axios 会在非 2xx 时 reject。Intl.DurationFormat 目前是 Newly available，并于 2025 年 3 月登陆所有主要引擎。

文章提到的 60–90 KB 典型依赖节省量更像观察结果而非正式研究，不应视为基准数据。原始资料在 UI Primitives 部分中断，因此 body-scroll-lock 和锚点定位的完整讨论没有包含在本篇摘要中。
