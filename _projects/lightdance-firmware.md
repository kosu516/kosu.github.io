---
layout: page
title: LightDance Firmware
description: ESP32 firmware for timed LED playback in NTU EE LightDance performances. ｜ Winter 2025
img: assets/img/projects/lightdance-firmware.jpg
period: "2025-12"
---

## Introduction

NTU EE LightDance uses timed LED animations in its stage performances. Our firmware team is replacing the eight-year-old Raspberry Pi playback system with custom ESP32 firmware. I implemented the initial Player module that runs the animations.

{% include figure.liquid path=page.img class="project-hero" loading="eager" alt="A LightDance performer and stage props outlined in colored LEDs" %}

## Playback control

The Player queues commands for its state machine, which handles transitions such as playing, pausing, stopping, and releasing playback resources. This also gives the firmware a test mode for checking LED output independently of a show timeline.

## Rendering LED frames

On each playback clock tick, the frame buffer uses the current and next animation keyframes to compute the LED colors. It interpolates fades in HSV and applies gamma and brightness correction before passing the result to the LED controller.

[GitHub repository](https://github.com/YuHsuan0116/LightDance_Firmware) · [Player documentation](https://github.com/YuHsuan0116/LightDance_Firmware/tree/main/legacy/LPS/components/Player/docs) · [Watch a LightDance performance](https://youtu.be/XBgxhFKJCHk)
