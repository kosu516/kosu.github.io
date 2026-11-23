---
layout: page
title: Pose-Guided Proportional Structure Assessment
description: A pose-aware model that scores proportional similarity in 2D character illustrations. ｜ Fall 2025
img: assets/img/projects/pose-guided-proportional-assessment.jpg
importance: 2
---

{% include figure.liquid path=page.img class="project-hero" loading="eager" alt="Original and altered character skeletons compared with a Grad-CAM heat map" %}

**Machine Learning · Computer Vision**

This project compares the body proportions of illustrated characters by aligning their estimated skeletons and scoring proportional similarity with a Siamese convolutional neural network. Grad-CAM highlights regions of the illustration that influenced the assessment.

The repository includes two alignment approaches, a deterministic pipeline and a learned spatial transformer network. It also includes tools for applying geometric transformations to images and skeletons to generate test cases with distorted proportions.

[GitHub repository](https://github.com/ML-1141/pose-guided-proportional-assessment)
