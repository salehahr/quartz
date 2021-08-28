---
title: Modelling noise and bias for IMU
date: "2021-04-23"
tags:
  - -sa/processed
  - sensors/IMU
---

Parent: [IMU index](imu index.md), [imu-measurement-model](imu-measurement-model.md)
Source: [MKok 2017 Using inertial sensors for position and orientation estimation](mkok 2017 using inertial sensors-for-position-and-orientation-estimation.md)

Modelling the noise
The noise not only represents measurement noise, but also model uncertainty.

With proper calibration, the three gyroscope axes are independent:
![unknown_filename.1.png](./_resources/Modelling_noise_and_bias_for_IMU.resources/unknown_filename.1.png)
Same for accelerometer — assume ![unknown_filename.3.png](./_resources/Modelling_noise_and_bias_for_IMU.resources/unknown_filename.3.png) diagonal for a properly calibrated sensor

Modelling the biases — two approaches

*   treat bias as constant (due to short experiment times)
    *   pre-calibrate in a separate experiment, or
    *   make part of the parameters vector
*   treat as slowly time-varying (due to long experiment times or shorter bias stability)
    *   make the bias part of the state vector
    *   model the bias as a random walk
        ![unknown_filename.2.png](./_resources/Modelling_noise_and_bias_for_IMU.resources/unknown_filename.2.png)         ![unknown_filename.png](./_resources/Modelling_noise_and_bias_for_IMU.resources/unknown_filename.png)

