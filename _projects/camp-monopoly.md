---
layout: page
title: Monopoly Game Website
description: Full-stack updates and automated record backups for the 2026 NTU EE camp game. ｜ Summer 2026
img: assets/img/projects/camp-monopoly-thumbnail.png
detail_image: assets/img/projects/camp-monopoly.jpg
period: "2026-07"
---

## Introduction

This website runs a Monopoly-style game for high school students at the NTU Electrical Engineering camp. I helped update the game mechanics and administrative tools for the 2026 camp.

{% include figure.liquid path=page.detail_image class="project-hero" loading="eager" alt="Illustrated banner for the 2026 NTU Electrical Engineering camp" %}

## Game rules and staff controls

The site uses a React frontend, an Express backend, and MongoDB for game state. I translated revised camp rules into updates across the frontend and backend, including how the game accounts for team assets and how staff manage play.

## Game-state backups

After an earlier data-loss incident, I added automated Google Sheets backups. The backup code snapshots team balances, land ownership, resources, and the active event from MongoDB, then writes them into spreadsheet tabs that staff can review.

[Website demo](https://kosu516.github.io/camp_monopoly/#/) · [GitHub repository](https://github.com/liftleaf1105/camp_monopoly)
