---
title: Basic EKF for SLAM
date: "2020-07-27"
tags:
  - filters/EKF
  - -sa/processed
  - -published
---

**Source**: [SLAM for Dummies](bibliography/riisgaard-slam-for-dummies.md)

A basic EKF implementation of [SLAM](SLAM/what-is-slam.md)   consists of multiple parts:

*   [Landmark extraction](SLAM/landmark-extraction.md)
*   [Data association](SLAM/data-association.md)

1.  After odometry change (due to robot moving), [state estimation](SLAM/ekf-1-prediction.md) from odometry
2.  [Update of the estimated state using re-observed landmark data](studienarbeit/ekf-2-reobservation.md)
3.  [Update landmark database with new landmarks](studienarbeit/ekf-3-new-landmarks.md)

Note: at any point in the three steps on the left, the EKF will have an estimate of the robots current position

![Image.png](studienarbeit/_resources/Basic_EKF_for_SLAM.resources/Image.png)

