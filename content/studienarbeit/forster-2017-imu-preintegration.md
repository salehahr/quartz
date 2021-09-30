---
title: Forster 2017 IMU Preintegration
date: "2020-11-17"
tags:
  - to-do/to-clarify
  - -resources/-bibliography
  - -resources/-bibliography/bib-to-read
  - -sa/processed
  - sensors/IMU/preintegration
---

Authors: Forster et al

Abstract:

*   First contribution: preintegration theory (building up on Lupton's work)
    *   what's different from Lupton's:
        *   addresses manifold structure of the rotation group, analytic derivation of all Jacobians
        *   Lupton's work uses Euler angles
        *   Using Euler angles and techniques of Euclidian spaces for state propagation/covariance estimation is not properly invariant under rigid transformations
        *   uncertainty propagation, a-posteriori bias correction
    *   same as Lupton: integration performed in local frame, eliminating need for reintegrating when linearisation point changes
*   Second contribution: integration of the preintegrated IMU model into a visual-inertial pipeline
*   The system presented uses incremental smoothing for fast computation of the optimal MAP estimate
*   Uses structureless model (3D landmarks are not part of the variables to be estimated)
*   for visual measurements --> allows eliminating large numbers of variables

Motivation:

*   optimisation-based approaches are more accurate than filtering-based ones, but come at the cost of high computational complexity
*   preintegration theory allows reduction of the computational complexity by accurately summarising multiple inertial measurements into a single relative motion constraint

IMU preintegration over frames
![unknown_filename.png](./_resources/[Forster_2017]_IMU_Preintegration.resources/unknown_filename.png)

Introduction
[Why use the visual-inertial sensor combination?](why-use-the-visual-inertial-sensor-combination_.md)
[Handling the computational complexity of optimisation-based SLAM](handling the-computational-complexity-of-optimisation-based-slam.md)

Preliminaries
[SO(3) 3D rotation group](so(3) 3d rotation group.md), [lie group,-lie-algebra](rotations/lie-group-lie-algebra.md)
  [Exponential map](rotations/exponential-map.md)

  [Logarithm map](rotations/logarithm-map.md)

[SE(3) Special Euclidian Group](se(3)-special-euclidian-group.md)
[Gauss-Newton Method on Manifold](gauss-newton-method-on-manifold.md)

MAP VI state estimation
[System in a VIN problem with IMU preintegration](system in a-vin-problem-with-imu-preintegration.md)
[MAP estimation](map-estimation.md)

IMU model and motion integration
[IMU kinematic model using Euler integration](imu-kinematic-model-using-euler-integration.md)
[IMU preintegration on manifold](imu-preintegration-on-manifold.md)

Preintegration math
- [ ] To do...

