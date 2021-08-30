---
title: Preintegration of IMU
date: "2020-10-20"
tags:
  - sensors/IMU
  - sensors/IMU/preintegration
  - -sa/to-be-processed
---

Parent: [IMU](sensors/imu.md)
Backlinks: [IMU states, dynamics equations](studienarbeit/imu-states-dynamics-equations.md)

*   IMU measurements arrive at a higher frequency (frame rate) compared to camera captures (keyframe rate)
*   IMU measurements constrain consecutive states
*   We want to summarise these 'in-between' IMU measurements into one single relative motion constraint between keyframes

