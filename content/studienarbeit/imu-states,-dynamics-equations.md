---
title: IMU states, dynamics equations
date: "2021-04-23"
tags:
  - -sa/processed
  - sensors/IMU
---

Parent: [IMU index](imu-index.md)
Source: [Mur-Artal 2017 VI-ORB](mur-artal-2017-vi-orb.md)

Evolution of IMU states (world frame to IMU: orientation R, position p, velocity v) between consecutive keyframes

![unknown_filename.1.png](./_resources/IMU_states,_dynamics_equations.resources/unknown_filename.1.png)

Evolution of IMU states (world frame to IMU: orientation R, position p, velocity v) between consecutive frames

Using the [preintegration](preintegration.md) terms ![unknown_filename.png](./_resources/IMU_states,_dynamics_equations.resources/unknown_filename.png) 
![unknown_filename.2.png](./_resources/IMU_states,_dynamics_equations.resources/unknown_filename.2.png)

Preintegration (delta) terms and the Jacobians can be computed iteratively as IMU measurements arrive (s. Forster's paper on preintegration)

