---
title: Why use the visual-inertial sensor combination?
date: "2020-10-20"
tags:
  - SLAM/multisensor-SLAM
  - -sa/processed
---

Parent: [SLAM Index](slam-index.md)
See also: [Multisensor fusion](multisensor-fusion.md)

Source: [Mur-Artal 2017 VI-ORB](mur-artal-2017-vi-orb.md)

*   Cheap but also with good potential
*   Cameras provide rich information but are relatively cheap
*   [IMU](imu.md)
    *   provides self-motion info, helps recover scale in monocular applications
    *   enables estimation of the direction of gravity --> renders pitch and roll observable

* * *

Source: [Forster 2017 IMU Preintegration](forster-2017-imu-preintegration.md)

*   Visual-inertial fusion for 3D structure and motion estimation
*   Both cameras and IMUs are cheap, easy to find and complement each other well
*   Camera
    *   exteroceptive sensor
    *   measures, up to a to-be-determined metric scale, appearance and geometrical structure of a 3D scene
*   IMU
    *   interoceptive sensor
    *   makes metric scale of monocular cameras, as well as the direction of gravity, observable

* * *

Source: [Wu 2018 Image-based camera localization: an overview](wu 2018-image-based-camera-localization_-an-overview.md)

*   Cameras provide rich information of a scene
*   IMU provide odometry
    *   self-motion information and
    *   accurate short-term motion estimates at high frequency

* * *

Source: \[Mirzaei 2008\] A Kalman Filter-Based Algorithm for IMU-Camera Calibration: Observability Analysis and Performance Evaluation

Motivation
Inertial navigation systems (INSs) combine IMU with GPS. However, GPS is not always utilisable (e.g. indoor locations) --> cameras/visual sensors are used as an alternative.
Points in favour of cameras: small size, light-weight, passive sensors that provide rich information at low cost.

Cameras and IMUs are complementary in terms of accuracy and frequency response.

*   An IMU is ideal for tracking over
    *   short periods of time
    *   motions with high dynamic profile
*   A camera is best suited for
    *   state estimation over longer periods of time
    *   smoother motion profiles

