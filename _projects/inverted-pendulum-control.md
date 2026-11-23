---
layout: page
title: Inverted Pendulum Control
description: Autonomous swing-up, PID balancing, and recovery on a physical inverted pendulum. ｜ Fall 2026
img: assets/img/projects/inverted-pendulum.jpg
importance: 1
---

{% include figure.liquid path=page.img class="project-hero" loading="eager" alt="Two physical inverted-pendulum setups" %}

**Automatic Control · Reinforcement Learning**

I used a LabVIEW state machine to move the pendulum from swing-up to PID stabilization and to trigger recovery after a disturbance. The state machine handled the transitions automatically so the system could resume balancing without manual intervention.

I also implemented a deep Q-network (DQN) controller on the physical pendulum, using MuJoCo simulation to support hardware experiments. The playlist includes demonstrations of swing-up and balancing, disturbance recovery, and DQN control.

[Watch the YouTube playlist](https://www.youtube.com/playlist?list=PLUr_lWGUlEg0)

GitHub repository: TBD
