---
layout: page
title: Pose-Guided Proportional Structure Assessment
description: A pose-aware model that scores proportional similarity in 2D character illustrations. ｜ Fall 2025
img: assets/img/projects/pose-guided-proportional-assessment.jpg
period: "2025-09"
---

## Introduction

We built a model to compare body proportions in 2D character illustrations, even when the characters are drawn in different poses. It outputs a similarity score and a heat map showing which regions influenced the assessment.

{% include figure.liquid path=page.img class="project-hero" loading="eager" alt="Original and altered character skeletons compared with a Grad-CAM heat map" %}

## Pose alignment and similarity scoring

The pipeline estimates a skeleton for each character and aligns the skeletons before comparing proportions. We implemented two ways to align them, using a deterministic geometric pipeline and a learned spatial transformer network (STN). A Siamese convolutional neural network then scores the similarity of the pair.

## Distortion tests and visualization

We generated test cases by applying geometric changes to skeletons and illustrations, such as rescaling one body region or applying a local swirl. We used Grad-CAM to inspect which regions affected the model’s score and compare them with the areas we deliberately distorted.

[GitHub repository](https://github.com/ML-1141/pose-guided-proportional-assessment) · [Poster]({{ '/assets/pdf/pose-guided-proportional-assessment-poster.pdf' | relative_url }}) · [Paper]({{ '/assets/pdf/pose-guided-proportional-assessment-paper.pdf' | relative_url }})
