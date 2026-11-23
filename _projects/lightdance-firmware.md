---
layout: page
title: LightDance Firmware
description: ESP32 firmware for timed LED playback in NTU EE LightDance performances. ｜ Fall 2026
img: assets/img/projects/lightdance-firmware.jpg
importance: 4
---

{% include figure.liquid path=page.img class="project-hero" loading="eager" alt="A LightDance performer and stage props outlined in colored LEDs" %}

**Embedded Systems · ESP32**

The LightDance firmware team is replacing an eight-year-old Raspberry Pi playback system with custom ESP32 firmware. I implemented the initial Player module, translating animation data into timed LED frames and coordinating playback with a state machine.

The Player coordinates a playback clock, a frame buffer, and a separate LED controller. Playback commands pass through the state machine, and clock ticks determine which frame the LED controller displays.

[GitHub repository](https://github.com/YuHsuan0116/LightDance_Firmware) · [Player documentation](https://github.com/YuHsuan0116/LightDance_Firmware/tree/main/legacy/LPS/components/Player/docs) · [Watch a LightDance performance](https://youtu.be/XBgxhFKJCHk)
