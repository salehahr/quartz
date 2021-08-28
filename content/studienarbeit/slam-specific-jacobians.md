---
title: SLAM-specific jacobians
date: "2020-07-29"
tags:
  - filters/EKF
  - -sa/processed
---

Source: [SLAM for Dummies](slam-for-dummies.md)
Backlinks:  [EKF matrices/vectors](ekf-matrices_vectors.md)

Jxr

*   Jacobian of the prediction of landmarks, which does not include prediction of theta, w.r.t. robot POSE
*   same as J\_prediction model, except without rotation term
    ![unknown_filename.png](./_resources/SLAM-specific_jacobians.resources/unknown_filename.png)
    

Jz
Jacobian of prediction of landmarks, but w.r.t. \[range, bearing\]
![unknown_filename.1.png](./_resources/SLAM-specific_jacobians.resources/unknown_filename.1.png)

