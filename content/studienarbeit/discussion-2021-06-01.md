---
title: Discussion 2021-06-01
date: "2021-06-07"
tags:
  - -sa/processed
  - discussion/2021/2021-06
---

Notes

*   IMU data to be generated using kinematic relations, not via numerical differentiation
    *   Reduce loss of data, model for prediction, noise propagation
*   Forward kinematics B --> C (everything in terms of SLAM coordinates), s. [Probe forward kinematics](probe-forward-kinematics.md)
*   For visualisation: IMU data in W coordinates
*   Monday: real probe
*   Python robotics toolboxes for generating of forward kinematics matrices, velocity expressions (symbolic differentiation)

Predict step

1.  Kinematics ([equations of motion IMU to camera](equations-of-motion-imu-to-camera.md))  = f(DOF)
    p\_BC = f(l1, l2)
    v\_BC = f(ang\_vel)
    a\_BC = f(acc)
    
    OR
    
    Forward kinematics
    
2.  Get IMU data from above step
    IMU = (ang\_vel, acc)
    s.  [Chaining rotation matrices and angular velocities](chaining-rotation-matrices-and-angular-velocities.md) to get om\_B from om\_C, om\_BC
    
3.  Prediction equation
    x\_dot = f(ang\_vel, acc)
    
    x = \[p\_B, v\_B, rot\_B, DOF\]
    

![unknown_filename.png](./_resources/Discussion_2021-06-01.resources/unknown_filename.png)

