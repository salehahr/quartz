---
title: Landmark extraction
date: "2020-08-06"
tags:
  - localisation/landmarks
  - -sa/processed
---

Source: [SLAM for Dummies](slam-for-dummies.md)
Backlinks: [Basic EKF for SLAM](basic-ekf-for-slam.md), [nearest-neighbour](nearest-neighbour.md)

Basic [landmark](landmarks.md) extraction using a laser scanner

1.  [Spike algorithm](spike-algorithm.md)
2.  [RANSAC](ransac.md) ([ekf](ekf.md) handles points)
3.  Expansion of RANSAC so that EKF handles lines
4.  Scan-matching: two successive laser scans are matched

Spike and RANSAC are good for indoor environments

