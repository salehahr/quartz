---
title: Kalman gain for EKF
date: "2020-08-06"
tags:
  - filters/EKF
  - -sa/processed
---

Source: [SLAM for Dummies](slam-for-dummies.md)
Backlinks:  [EKF matrices](ekf-matrices.md)

How much we will trust the observed landmarks

*   compromise between odometry and landmark correction
*   uses
    *   uncertainty of observed landmarks
    *   measure of quality of the range measurement device
    *   odometry performance

Gains for range and brearing (3+2n x 2)

![unknown_filename.png](./_resources/Kalman_gain_for_EKF.resources/unknown_filename.png)

