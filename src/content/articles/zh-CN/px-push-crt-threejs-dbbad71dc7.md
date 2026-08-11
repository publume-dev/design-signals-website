---
decisionKey: "dbbad71dc76fc5f78517b965655483ae2214b5d1a506eac13a94775a686a169c"
language: "zh-CN"
title: "构建 PX PUSH 网站：CRT 效果、Three.js 场景与滚动驱动细节"
summary: "Codrops 的一篇案例研究记录了 PX PUSH 网站如何叠加 CRT 效果、协调 Three.js 场景并加入滚动驱动交互，详细展示了这些效果的实现方法。"
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

据这篇 Codrops 案例研究介绍，该网站的 CRT 效果由多层固定叠加组成：扫描线、重复线纹理、背景模糊发光、crt.png 暗角以及动态噪点。文章还描述了三个相互独立的 Three.js 场景——拉伸的镀铬标志、云端飞行主视觉和软盘——它们通过发布/订阅生命周期相互协调，让页面在所有场景加载完成后才展示内容。

在 About 页面，滚动速度决定了创始人的呈现方式：他们会轮换 15 个拍摄角度，滚动累加器会像角色选择界面一样切换图像。

Journal 抽屉使用 CSS 遮罩制作打孔效果，维护独立的 Lenis 实例，并保留每篇文章的 slug、canonical URL 和 BlogPosting schema。Marquee 标题通过声明式属性系统绑定 GSAP 时间线，在区块进入和离开视口时随机显示单词并模糊淡出。

这篇文章没有提供 WebGL 效果的性能指标或用户测试数据，因此这些效果在中低端设备上的实际影响尚未得到验证。
