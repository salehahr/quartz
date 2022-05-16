---
title: Solà 2017 Quaternion kinematics for ESKF
date: "2021-05-14"
tags:
  - -resources/-bibliography
  - -resources/-bibliography/bib-read
  - -sa/processed
  - -published
---

**Link**: <http://www.iri.upc.edu/people/jsola/JoanSola/objectes/notes/kinematics.pdf>  
**Author**: Joan Solà  

## Abstract
*   Primer on quaternion/rotation group math
*   Math for error state Kalman filters using IMUs

## Contents/Chapters

1.  [Unit quaternions](math/rotations/unit-quaternions.md), [double cover](math/rotations/quaternion-double-cover.md)
2.  Rotations, s. also [SO(3) 3D rotation group](math/rotations/so3-3d-rotation-group.md)
3.  [Quaternion conventions](quaternion-conventions.md)
4.  Perturbations, derivatives, integrals
5.  [Error-State Kalman Filter](studienarbeit/50.5-error-state-kalman-filter.md) for IMU-driven systems
    *   [Variables in ESKF](studienarbeit/50.5.1.1-states-of-the-eskf-for-estimating-imu-pose.md)
    *   [IMU measurement model](studienarbeit/40.1-imu-measurement-model.md)
    *   [IMU motion model](studienarbeit/50.3-modelling-imu-in-kf.md)
        * [The initial gravity vector/orientation for the IMU ESKF](studienarbeit/50.5.1.2-the-initial-gravity-vector-orientation-for-the-imu-eskf.md)
    *   [IMU nominal-state and error-state kinematics](studienarbeit/50.5.1-imu-nominal-state-and-error-state-kinematics.md)
    *   [IMU ESKF prediction equations](studienarbeit/50.6-eskf-prediction-equations.md)
6.  [Fusing IMU + other sensors](studienarbeit/50.7-eskf-update-fusing-imu-with-complementary-sensory-data.md)
7.  ESKF using global angular errors

