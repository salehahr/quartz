---
title: IMU preintegration on manifold
date: "2020-11-27"
tags:
  - to-do/to-clarify
  - -sa/processed
  - sensors/IMU
  - sensors/IMU/preintegration
---

Parent: [IMU index](imu-index.md)
Source: [Forster 2017 IMU Preintegration](forster-2017-imu-preintegration.md)
Backlinks: [IMU model](imu-model.md)

Preintegration on manifold

*   Summarising all measurements between the keyframes i and j into a single measurement
*   This preintegrated IMU measurement constrains the motion between two consecutive keyframes
*   Assume IMU is synchronised with the camera

![unknown_filename.11.png](./_resources/IMU_preintegration_on_manifold.resources/unknown_filename.11.png)

*   The above equations already provide the summarised IMU measurements,
*   however, the integration has to be repeated whenever the linearisation point at t=t\_i changes
    *   i.e., change in R\_i impolies change in all future rotations
    *   would imply reevaluating the summations and products for each step!
    *   we want to avoid this (repeated integrations) --> try to define the relative motion increments without using pose or velocity at t\_i

![unknown_filename.3.png](./_resources/IMU_preintegration_on_manifold.resources/unknown_filename.3.png)
![unknown_filename.6.png](./_resources/IMU_preintegration_on_manifold.resources/unknown_filename.6.png)
![unknown_filename.png](./_resources/IMU_preintegration_on_manifold.resources/unknown_filename.png)

This is better, but there is still a dependency on the biases

*   Solve the problem in two steps
*   First assume b\_i is known

Preintegrated IMU measurements
![unknown_filename.8.png](./_resources/IMU_preintegration_on_manifold.resources/unknown_filename.8.png)![unknown_filename.5.png](./_resources/IMU_preintegration_on_manifold.resources/unknown_filename.5.png)
(using the properties of the exponential map: perturbations, adjoint)
With

*   ![unknown_filename.2.png](./_resources/IMU_preintegration_on_manifold.resources/unknown_filename.2.png) preintegrated rotation measurement
*   ![unknown_filename.1.png](./_resources/IMU_preintegration_on_manifold.resources/unknown_filename.1.png) noise of the preintegrated rotation measurement

Also,
![unknown_filename.7.png](./_resources/IMU_preintegration_on_manifold.resources/unknown_filename.7.png)![unknown_filename.9.png](./_resources/IMU_preintegration_on_manifold.resources/unknown_filename.9.png)
![unknown_filename.10.png](./_resources/IMU_preintegration_on_manifold.resources/unknown_filename.10.png)![unknown_filename.4.png](./_resources/IMU_preintegration_on_manifold.resources/unknown_filename.4.png)

Subbing these back into the equations above, we obtain the preintegrated measurements
![unknown_filename.12.png](./_resources/IMU_preintegration_on_manifold.resources/unknown_filename.12.png)
(function of the to-be estimated state and a random noise)

