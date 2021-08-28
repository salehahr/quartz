---
title: Jeon 2009 Kinematic Kalman Filter for Robot End-Effector Sensing
date: "2021-05-26"
tags:
  - -resources/-bibliography
  - -resources/-bibliography/bib-read
  - discussion/2021/2021-05
  - -sa/to-be-processed
---

Backlinks: [Discussion 2021-05-25](discussion-2021-05-25.md)

Authors: Jeon and Tomizuka

Abstract

*   inaccuracies in estimation of EE motion can come from kinematic error (error in parameters in kinematic equations)
    *   to overcome this: take direct measurements e.g. using vision, but vision has high latency
    *   IMUs are used to provide interframe data
*   fuse camera and IMU in a kinematic Kalman filter (KKF) framework.
    Note: uses ESKF
    
*   effect of camera measurement delay, augmenting the KF states to also estimate the time delay

|     |     |
| --- | --- |
| ![unknown_filename.1.png](./_resources/[Jeon_2009]_Kinematic_Kalman_Filter_for_Robot_End-Effector_Sensing.resources/unknown_filename.1.png) | ![unknown_filename.png](./_resources/[Jeon_2009]_Kinematic_Kalman_Filter_for_Robot_End-Effector_Sensing.resources/unknown_filename.png) |

