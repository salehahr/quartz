---
title: Discussion 2021-05-25
date: "2021-05-25"
tags:
  - -sa/processed
  - discussion/2021/2021-05
---

Backlinks: [Discussion 2021-05-10](discussion-2021-05-10.md), [discussion-2021-05-21](discussion-2021-05-21.md)

Notes

*   IMU-rod transformation: rotation part (spherical joint), translation part
*   predict and update equations?
*   maybe change variables in states vector to local coordinates
*   add gravity later
*   Ausblick: Einfluss der IMU auf verbesserte Lokalisierung --> evtl eine IMU Koordinate weglassen

Next:
- [x] ~~generate fake imu data~~ (delegated, s. [obtaining imu measurements from camera by forward kinematics](obtaining imu measurements-from-camera-by-forward-kinematics.md))
- [x] look for existing literature on IMU fusion/EKF which uses kinematic relations
- [x] Massenmatrix, Koriolisterme etc.
![unknown_filename.2.png](./_resources/Discussion_2021-05-25.resources/unknown_filename.2.png)

Gedachtjes
misschien zouden de onbekende hoeken theta\_1:3 uit de spherical joint direct in de toestandsvector terrible idea, nonlinearity

Stuff to read:

*   [Jeon 2009 Kinematic Kalman Filter for Robot End-Effector Sensing](jeon 2009 kinematic kalman-filter-for-robot-end-effector-sensing.md)
*   Calibration of DH-params (skimmed, scrapped)
    *   Du2014 - Online robot calibration based on hybrid sensors using Kalman Filters
    *   Lee 2012 - Geometrical Derivation  of Differential Kinematics  to Calibrate Model Parameters  of Flexible Manipulator
*   Misc
    *   Du2013 - IMU-based online kinematic calibration of robot manipulator
    *   Du2013 - Online robot calibration based on vision measurement
    *   Kim 2004 - Initial calibration of an inertial measurement unit using an optical position tracking system

Anhang

![unknown_filename.1.png](./_resources/Discussion_2021-05-25.resources/unknown_filename.1.png)

![unknown_filename.jpeg](./_resources/Discussion_2021-05-25.resources/unknown_filename.jpeg)

