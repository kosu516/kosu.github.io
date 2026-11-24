---
layout: page
title: Inverted Pendulum Control
description: Autonomous swing-up, PID balancing, and recovery on a physical inverted pendulum. ｜ Fall 2026
img: assets/img/projects/inverted-pendulum.jpg
period: "2026-09"
---

## Introduction

I built two controllers for a physical inverted pendulum. The experiments explored how to swing the pendulum upright, keep it balanced, and recover when a disturbance breaks that balance.

{% include figure.liquid path=page.img class="project-hero" loading="eager" alt="Two physical inverted-pendulum setups" %}

## Swing-up, balance, and recovery

I used a LabVIEW state machine to coordinate swing-up and stabilization. The swing-up controller first brings the pendulum near upright, where a PID controller takes over to hold it there. If a disturbance knocks the pendulum out of balance, the state machine triggers recovery and returns the system to balancing without a manual reset.

## Reinforcement learning on hardware

I also implemented a deep Q-network (DQN) controller on the physical pendulum, with MuJoCo simulation supporting the hardware experiments. The demos show classical swing-up and balancing, recovery after a disturbance, and DQN control.

[Watch the YouTube playlist](https://www.youtube.com/playlist?list=PLUr_lWGUlEg0)
