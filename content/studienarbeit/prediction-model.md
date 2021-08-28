---
title: Prediction model
date: "2020-07-29"
tags:
  - filters/EKF
  - -sa/processed
---

Source: [SLAM for Dummies](slam-for-dummies.md)
Backlinks:  [EKF matrices/vectors](ekf-matrices_vectors.md)

Used in the [prediction step](prediction-step.md)

How to compute an expected position of the robot given the old position and the control input (so basically based on [odometry](http://www.evernote.com/shard/s484/nl/217355218/d6e4227d-18b0-4633-9967-b72012e0cd6b))
Control terms are deltax, deltay, deltatheta)
![unknown_filename.png](./_resources/Prediction_model.resources/unknown_filename.png)![unknown_filename.1.png](./_resources/Prediction_model.resources/unknown_filename.1.png)
deltat - change in thrust
q - error term

Jacobian (assuming linearised version)
![unknown_filename.2.png](./_resources/Prediction_model.resources/unknown_filename.2.png)
Not extended for landmarks because only used for robot position prediction

