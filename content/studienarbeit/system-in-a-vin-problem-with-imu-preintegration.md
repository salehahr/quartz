---
title: System in a VIN problem with IMU preintegration
date: "2020-11-27"
tags:
  - SLAM
  - -sa/processed
  - sensors/IMU
---

Source: [Forster 2017 IMU Preintegration](forster-2017-imu-preintegration.md)

![Image.png](./_resources/System_in_a_VIN_problem_with_IMU_preintegration.resources/Image.png)

State x\_i of the system at time i
![unknown_filename.png](./_resources/System_in_a_VIN_problem_with_IMU_preintegration.resources/unknown_filename.png)

with
![unknown_filename.1.png](./_resources/System_in_a_VIN_problem_with_IMU_preintegration.resources/unknown_filename.1.png)
![unknown_filename.2.png](./_resources/System_in_a_VIN_problem_with_IMU_preintegration.resources/unknown_filename.2.png)
![unknown_filename.3.png](./_resources/System_in_a_VIN_problem_with_IMU_preintegration.resources/unknown_filename.3.png)

|     |     |
| --- | --- |
| ![unknown_filename.4.png](./_resources/System_in_a_VIN_problem_with_IMU_preintegration.resources/unknown_filename.4.png) | All keyframes up till time k |
| ![unknown_filename.5.png](./_resources/System_in_a_VIN_problem_with_IMU_preintegration.resources/unknown_filename.5.png) | State of all keyframes |
| ![unknown_filename.6.png](./_resources/System_in_a_VIN_problem_with_IMU_preintegration.resources/unknown_filename.6.png) | camera measurements |
| ![unknown_filename.7.png](./_resources/System_in_a_VIN_problem_with_IMU_preintegration.resources/unknown_filename.7.png) | IMU measurements between KFs i and j (consecutive) |
| ![unknown_filename.8.png](./_resources/System_in_a_VIN_problem_with_IMU_preintegration.resources/unknown_filename.8.png) | Set of measurements up till time k |

IMU pose: ![unknown_filename.9.png](./_resources/System_in_a_VIN_problem_with_IMU_preintegration.resources/unknown_filename.9.png), maps a point in B to W

