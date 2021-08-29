---
title: Landmark extraction
date: "2020-08-06"
tags:
  - localisation/landmarks
  - -sa/processed
  - -published
---

**Source**: [SLAM for Dummies](bibliography/riisgaard-slam-for-dummies.md)

Basic [landmark](SLAM/landmarks.md) extraction using a laser scanner

1.  [Spike algorithm](SLAM/spike-landmarks.md)
2.  [RANSAC](SLAM/ransac.md) ([EKF](SLAM/basic-ekf-for-slam.md) handles points)
3.  Expansion of RANSAC so that EKF handles lines
4.  Scan-matching: two successive laser scans are matched

Spike and RANSAC are good for indoor environments