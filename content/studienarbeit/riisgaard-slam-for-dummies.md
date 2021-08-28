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
---

Authors:  Søren Riisgaard and Morten Rufus Blas
Parent: [SLAM resources](slam-resources.md)

Abstract:

*   Tutorial introduction to SLAM, with minimal prerequisites for the understanding of SLAM as explained here
*   Mostly explains a single approach to the steps involved in SLAM
*   Complete solution for SLAM using EKF (extended Kalman filter)
*   Only considers 2D motion, not 3D

Chapters

3.  [What is SLAM?](what-is-slam_.md)
4.  [Overview of SLAM using EKF](overview-of-slam-using-ekf.md)
5.  [Hardware](http://www.evernote.com/shard/s484/nl/217355218/8f5cd12b-ae15-479c-bbb2-99fff8ec0692)
    *   Robot
    *   Range measurement device
6.  [SLAM process](http://www.evernote.com/shard/s484/nl/217355218/dad6e2b1-b186-40d3-94f5-3064f1043376)
    1.  [Step 1: Odometry update](http://www.evernote.com/shard/s484/nl/217355218/fe366015-f610-46f9-a801-eb6deb8a839d)
    2.  [Step 2: Reobservation](http://www.evernote.com/shard/s484/nl/217355218/91e0df9b-526e-47e1-af42-65c105fb7f45)
    3.  [Step 3: Add new landmarks](http://www.evernote.com/shard/s484/nl/217355218/91e0df9b-526e-47e1-af42-65c105fb7f45)
7.  Laser data
8.  [Odometry data](http://www.evernote.com/shard/s484/nl/217355218/d6e4227d-18b0-4633-9967-b72012e0cd6b)
9.  [Landmarks](http://www.evernote.com/shard/s484/nl/217355218/e3082edf-ff56-4e86-8fe8-4d6e3995fbcc)
10.  [Landmark extraction](landmark-extraction.md)
    1.  [Spike algorithm](http://www.evernote.com/shard/s484/nl/217355218/6a599923-7f8a-4982-95df-d6ab2b88658c)
    2.  [RANSAC](http://www.evernote.com/shard/s484/nl/217355218/78822a3d-a9b1-40e3-b580-e0af94697de9)
11.  [Data association](http://www.evernote.com/shard/s484/nl/217355218/eb7cb553-374f-4000-a218-ceb503c046d8)
12.  [EKF](http://www.evernote.com/shard/s484/nl/217355218/2b2f591f-ed5f-44e0-ba5c-0a3c00bcd84b)
    1.  [EKF matrices](ekf-matrices.md)
    2.  [Prediction model](prediction-model.md)
    3.  [Measurement model](http://www.evernote.com/shard/s484/nl/217355218/54e21e37-2184-46fe-b494-01ef63b3b2eb)
    4.  [SLAM-specific Jacobians](http://www.evernote.com/shard/s484/nl/217355218/81433821-2153-4b2c-ba42-4a37bfcbc9e3)
    5.  [Process noise](http://www.evernote.com/shard/s484/nl/217355218/dd75d924-7153-4b9f-81a1-ec6237d4ec25)
    6.  [Measurement noise](http://www.evernote.com/shard/s484/nl/217355218/fc4f284b-8751-4c90-9253-94898f905f97)
13.  Final remarks

Questions

*   [x] Under which classification does the algo. used here fall?
    *   multikind sensor
    *   filter-based, feature-based

