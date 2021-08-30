---
title: SA TODO
date: "2020-07-30"
tags:
  - to-do
  - -sounding-board
  - -master
  - -sa/processed
---

Parent: [Scope of Studienarbeit](scope-of-studienarbeit.md)
See also: [HiWi to-do](hiwi to-do.md), [defslam +-orbslam3-integration](defslam-+-orbslam3-integration.md)

Studienarbeit
Camera-based localisation

*   [x] Find a classification of approaches/techniques
    *   [x] Briefly describe each
    *   [ ] See if it applies to the project
*   [x] Look into the most promising approach -- how to implement (DefSLAM)
*   DefSLAM
    *   [x] Install DefSLAM library
    *   [x] Skim through an existing VI-SLAM (rigid) implementation to see how sensor fusion is done (as an overview for the coming sensor fusion task)
        *   [x] VINS-Mono, [VIORB](http://www.evernote.com/shard/s484/nl/217355218/014a8f28-8f7b-4178-aea8-c65f9ae1dd73) paper
    *   [x] Prepare dummy data for testing VI-SLAM (eventually VI-DefSLAM) — interpolate data between frames and add noise/bias
    *   [x] Go through code
        *   [x] Get the executables working
        *   [x] VideoCapture OpenCV problem -- reinstall with all FFMMPEG options
        *   [x] Figure out g2o
        *   [x] Go through the rest of DefSLAM
        *   [x] Go through the rest of ORBSLAM3
            *   IMU term in cost function
            *   IMU preintegration
            *   IMU initialisation
*   - [x] implement imu term in optimisation (either using ekf (s. [imu index](imu-index.md)), or [orbslam3-approach](orbslam3-approach.md)) for doing VI-DefSLAM. scrapped
*   [ ] Use EKF to estimate IMU calibration pose (between IMU and camera)
    *   [x] model for generating imu data from camera, s. [obtaining imu measurements from camera by forward kinematics](obtaining imu measurements-from-camera-by-forward-kinematics.md)
    *   [x] Come up with equations correlating SLAM CS to real camera CS: just subtract theta\_notch
    *   [x] Implement filter using IMU data + camera measurements

|     |     |
| --- | --- |
| Predict | Update |
| *   Get IMU data<br>    IMU = func(fwkine(DOF), kinem. relations(last cam val))<br>    *   Generate IMU data per time step<br>    *   IMU data generation to take into account cam-scope ang. displacement (q\_notch)<br>*   Propagate states (IMU states + DOF)<br>    states = func(IMU) | *   Measurements available<br>    *   Notch position<br>    *   SLAM pose<br>*   Correct SLAM pose to 'camera' pose at distal end of scope<br>*   Update states |

*   ~~- [x] Finalise interface (Python + DefSLAM)~~
    *   - [x] DefSLAM + SWIG scrapped for now
*   [ ] Make pretty plots/animations
*   [ ] Presentation
*   [ ] [Thesis](thesis/thesis.md)

