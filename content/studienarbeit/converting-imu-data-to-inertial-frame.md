---
title: Converting IMU data to inertial frame
date: "2021-07-23"
tags:
  - -sa/processed
  - sensors/IMU
  - math
---

Parent: [IMU index](imu-index.md)
Source: [http://redshiftlabs.com.au/wp-content/uploads/2018/02/an-1005\_-\_understanding\_euler\_angles.pdf](http://redshiftlabs.com.au/wp-content/uploads/2018/02/an-1005_-_understanding_euler_angles.pdf)

IMU outputs are in the body frame of the sensor.

*   Convention used in the article: yaw/psi (z) - pitch/theta (y) - roll/phi (x) around momentary axes
*   Momentary coordinate systems: W -> W' -> W'' -> B

Body acceleration to inertial acceleration
W\_a = R\_WB @ B\_a

Body angular rate to inertial angular rate

*   Each angular rate must be converted to the corresponding frame
    *   p: gyro\_z -> rotated into W: R\_w\_w' @ R\_w'\_w'' @ R\_w''\_B @ q
    *   q: gyro\_y -> rotated into W': R\_w'\_w'' @ R\_w''\_B @ q
    *   r: gyro\_x -> rotated into W'': R\_w''\_B @ r

![unknown_filename.1.png](./_resources/Converting_IMU_data_to_inertial_frame.resources/unknown_filename.1.png)
with
![unknown_filename.png](./_resources/Converting_IMU_data_to_inertial_frame.resources/unknown_filename.png)

Gimbal lock: pitch approaches +-90, terms divided by cos90

