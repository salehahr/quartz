---
title: Loose vs Tight coupling
date: "2020-07-30"
tags:
  - SLAM/multisensor-SLAM
  - -sa/processed
---

Parent: [SLAM Index](SLAM/slam_index.md)
Backlinks: [Multisensor fusion](multisensor-fusion.md)
Source: [Wu 2018 Image-based camera localization: an overview](wu 2018-image-based-camera-localization_-an-overview.md)

In loosely-coupled systems: all sensor states are independently estimated and optimized

*   easier to process frame and IMU data
*   less accurate/robust compared to tight coupling
*   e.g. Integrated IMU data can be incorporated as independent measurements in stereo vision optimization
*   e.g. Vision-only pose estimates are used to update an EKF so that IMU propagation can be performed

In tightly-coupled systems: all sensor states are jointly estimated and optimized

*   more difficult to process frame and IMU data
*   more accurate/robust compared to loose coupling

