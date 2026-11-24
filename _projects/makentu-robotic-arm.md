---
layout: page
title: Turkish Ice Cream Vendor Robot
description: A hand-tracking robotic arm that won the 2026 MakeNTU Best Maker Award. ｜ Spring 2026
img: assets/img/projects/makentu-robotic-arm.jpg
period: "2026-05"
---

## Introduction

Our team built a robotic arm that imitates a Turkish ice cream vendor. As someone reaches for the cone, the arm tracks their hand and moves the cone out of reach. I worked on the mechanism, hand tracking, and integration with motor control.

{% include figure.liquid path=page.img class="project-hero" loading="eager" alt="The orange robotic arm prototype with its wiring and motor controller" %}

## Hand tracking and motion control

A camera and MediaPipe run on a separate computer. The vision service sends hand detections to a FastAPI service on the Raspberry Pi over WebSocket. The Pi uses the incoming detections during the demo and controls the arm through a motor adapter. A mock adapter let us develop and test the software away from the physical arm.

Our prototype received the Best Maker Award among 44 teams at the MakeNTU Makerathon and earned NT$50,000 in prize money.

[GitHub repository](https://github.com/work-tomorrow/turkish-ice-cream) · [Demo video](https://drive.google.com/file/d/1BFXB1GpudO0woDzYfWKCwXtomD88cyo4/view)
