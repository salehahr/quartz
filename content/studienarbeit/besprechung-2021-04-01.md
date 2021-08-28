---
title: Besprechung 2021-04-01
date: "2021-04-01"
tags:
  - -sa/processed
  - discussion/2021/2021-04
---

Agenda

*   Recap: [last meeting (2021-03-15)](last-meeting-(2021-03-15).md)
    *   Offline Kalman — after this works, do a 'live' implementation on DefSLAM run
    *   IMU measurements as \[acc, gyro\] readings
        
        *   With noise, but without considering bias, IMU-cam transformation, gravity
        
    *   Two sets of measurements for filter: IMU measurements, DefSLAM (camera) measurements
    *   KF prediction using random walk
*   Recap: SLAM +filtering terminology (loose coupling, tight coupling)
*   Literature
*   Original suggestion using random walk model
*   Interface (DefSLAM, Python)
    *   read: OK
    *   write: to do
*   [x] Offline Kalman as a separate repo
*   Good papers?

Misc

*   python3 plot\_noisy\_traj.py
*   traj\_parser.py
*   Weiss PhD thesis
*   IMU tutorial
*   github msf-ekf
*

