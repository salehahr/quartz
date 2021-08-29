---
title: Riisgaard SLAM for dummies
date: "2020-07-27"
external_url: "http://dspace.mit.edu/bitstream/handle/1721.1/36832/16-412JSpring2004/NR/rdonlyres/Aeronautics-and-Astronautics/16-412JSpring2004/A3C5517F-C092-4554-AA43-232DC74609B3/0/1Aslam_blas_report.pdf"
tags:
  - -resources/-bibliography
  - SLAM
  - -resources/-bibliography/bib-read
  - -sa/processed
  - discussion/2020/2020-09
  - -published
---

Authors:  Søren Riisgaard and Morten Rufus Blas
Parent: [SLAM resources](slam-resources.md)

Abstract:

*   Tutorial introduction to SLAM, with minimal prerequisites for the understanding of SLAM as explained here
*   Mostly explains a single approach to the steps involved in SLAM
*   Complete solution for SLAM using EKF (extended Kalman filter)
*   Only considers 2D motion, not 3D

Chapters

3.  [What is SLAM?](SLAM/what-is-slam.md)
4.  [Overview of SLAM using EKF](overview-of-slam-using-ekf.md) 
5.  [Hardware](sensors/slam-hardware.md)
    *   Robot
    *   Range measurement device
6.  [SLAM process](http://www.evernote.com/shard/s484/nl/217355218/dad6e2b1-b186-40d3-94f5-3064f1043376)
    1.  [Step 1: Odometry update](SLAM/step-1-odometry-update-prediction-step.md)
    2.  [Step 2: Reobservation](studienarbeit/step-2-re-observation.md)
    3.  [Step 3: Add new landmarks](studienarbeit/step-3-new-landmarks.md)
7.  Laser data
8.  [Odometry data](http://www.evernote.com/shard/s484/nl/217355218/d6e4227d-18b0-4633-9967-b72012e0cd6b)
9.  [Landmarks](SLAM/landmarks.md)
10.  [Landmark extraction](SLAM/landmark-extraction.md)
    1.  [Spike algorithm](SLAM/spike-landmarks.md)
    2.  [RANSAC](SLAM/ransac.md)
11.  [Data association](SLAM/data-association.md)
12.  [EKF](SLAM/extended-kalman-filter.md)
    1.  [EKF matrices](studienarbeit/ekf-matrices-vectors.md)
    2.  [Prediction model](SLAM/prediction-model.md)
    3.  [Measurement model](studienarbeit/measurement-model.md)
    4.  [SLAM-specific Jacobians](studienarbeit/slam-specific-jacobians.md)
    5.  [Process noise](SLAM/50.2.1-process-noise-q-and-w-odometry.md)
    6.  [Measurement noise](studienarbeit/50.2.2-measurement-noise-r,-v-landmark.md)
13.  Final remarks

Questions

*   [x] Under which classification does the algo. used here fall?
    *   multikind sensor
    *   filter-based, feature-based

