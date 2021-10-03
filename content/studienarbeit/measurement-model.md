---
title: Measurement model
date: "2020-07-29"
tags:
  - filters/EKF
  - -sa/processed
---

Source: [SLAM for Dummies](slam-for-dummies.md)
Backlinks:  [EKF matrices/vectors](ekf-matrices_vectors.md)

Estimate of the range and bearing (from landmark) in  [Step 2: Re-observation](studienarbeit/ekf-2-reobservation.md)

![unknown_filename.png](./_resources/Measurement_model.resources/unknown_filename.png)

x, y, theta - current position estimate
lambdax, y - landmark position

Jacobian H w.r.t. x, y, theta (here for regular EKF, not for extended)
![unknown_filename.1.png](./_resources/Measurement_model.resources/unknown_filename.1.png)

In SLAM we need additional values for the landmarks
here for landmark number two in extended EKF
![unknown_filename.2.png](./_resources/Measurement_model.resources/unknown_filename.2.png)

*   Upper row is for information, not part of matrix
*   First three columns are regular H
*   Landmarks don't have any rotation

