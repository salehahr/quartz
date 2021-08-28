---
title: IMU index
date: "2020-10-20"
tags:
  - -master
  - -sa/processed
  - sensors/IMU
---

Parent: [SLAM Index](slam-index.md)
Backlinks: [SA TODO](sa-todo.md)

General
[IMU](imu.md)
[Odometry](odometry.md)
[Why use the visual-inertial sensor combination?](why-use-the-visual-inertial-sensor-combination_.md)
[IMU to camera coordinate transformations](imu-to-camera-coordinate-transformations.md)

**Practical**
[Converting IMU data to inertial frame](converting-imu-data-to-inertial-frame.md)

Modelling
[Probabilistic models for IMU](probabilistic-models-for-imu.md)
     [Choice of model for the IMU motion model](choice of model-for-the-imu-motion-model.md)
     [Choice of states for the IMU motion/kinematics model](choice of states-for-the-imu-motion_kinematics-model.md)
     [Variables in ESKF using IMUs](variables-in-eskf-using-imus.md)
[IMU states, dynamics equations](imu states, dynamics equations.md) (kfs and preintegration) / [(kok) imu motion model (discrete)]((kok) imu motion model (discrete).md) /  [(forster) imu kinematic model using euler]((forster) imu kinematic model using euler.md) / [(sola) imu-motion-model]((sola)-imu-motion-model.md)
     [The initial gravity vector/orientation for the IMU ESKF](the initial gravity-vector_orientation-for-the-imu-eskf.md)
     [IMU nominal-state and error-state kinematics](imu-nominal-state-and-error-state-kinematics.md)
[IMU measurement model](imu-measurement-model.md)
     [Assumptions in modelling the true angular velocity in IMUs](assumptions in modelling the-true-angular-velocity-in-imus.md)
     [Modelling noise and bias for IMU](modelling-noise-and-bias-for-imu.md)

ESKF
[IMU ESKF prediction equations](imu-eskf-prediction-equations.md)
[Fusing IMU with complementary sensory data](fusing-imu-with-complementary-sensory-data.md)

Preintegration
[Preintegration of IMU](preintegration-of-imu.md)
[IMU preintegration on manifold](imu-preintegration-on-manifold.md)

Fake data generation
[IMU data generation from camera/visual data](imu-data-generation-from-camera_visual-data.md)

Literature
[MKok 2017 Using inertial sensors for position and orientation estimation](mkok 2017 using inertial sensors-for-position-and-orientation-estimation.md)
[Forster 2017 IMU Preintegration](forster-2017-imu-preintegration.md)
[resource IMU common specifications, error models etc](resource imu-common-specifications,-error-models-etc.md)
<http://docs.openvins.com/propagation.html>

