---
title: Solà 2017 Quaternion kinematics for ESKF
date: "2021-05-14"
tags:
  - -resources/-bibliography
  - -resources/-bibliography/bib-read
  - -sa/processed
---

Link: <http://www.iri.upc.edu/people/jsola/JoanSola/objectes/notes/kinematics.pdf>

Author: Joan Solà
Abstract:

*   Primer on quaternion/rotation group math
*   Math for error state Kalman filters using IMUs

Contents/Chapters:

1.  [Quaternions](quaternions.md)
2.  Rotations, s. also [SO(3) 3D rotation group](so(3)-3d-rotation-group.md)
3.  [Quaternion conventions](quaternion-conventions.md)
4.  Perturbations, derivatives, integrals
5.  [Error-State Kalman Filter](error-state-kalman-filter.md) for IMU-driven systems
    *   [Variables in ESKF](variables-in-eskf.md)
    *   [IMU measurement model](imu-measurement-model.md)
    *   [IMU motion model](imu-motion-model.md)
        *   [The initial gravity vector/orientation for the IMU ESKF](the initial gravity-vector_orientation-for-the-imu-eskf.md)
    *   [IMU nominal-state and error-state kinematics](imu-nominal-state-and-error-state-kinematics.md)
    *   [IMU ESKF prediction equations](imu-eskf-prediction-equations.md)
6.  [Fusing IMU + other sensors](fusing-imu-+-other-sensors.md)
7.  ESKF using global angular errors

