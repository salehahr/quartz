---
title: IMU
date: "2021-04-23"
tags:
  - -sa/processed
  - sensors/IMU
  - -published
---

**Source**: [Mur-Artal 2017](bibliography/mur-artal-2017-vi-orb.md)

*   measures acceleration (from accelerometer) and angular velocity (from gyrometer) of sensor at regular intervals
*   measurements are affected by
    *   sensor noise
    *   accelerometer bias
    *   gyrometer bias
*   accelerometer is further affected by gravity --> need to subtract effect of gravity