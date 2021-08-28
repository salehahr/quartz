---
title: Basic EKF for SLAM
date: "2020-07-27"
tags:
  - filters/EKF
  - -sa/processed
---

Parent: [Extended Kalman Filter](extended-kalman-filter.md), [slam-index](slam-index.md)
Backlinks: [RANSAC](ransac.md)
See also: [What is SLAM?](what-is-slam_.md)

Source: [SLAM for Dummies](http://www.evernote.com/shard/s484/nl/217355218/3bc16d22-4339-40f5-9990-c019864b6e9a)

A basic EKF implementation of SLAM consists of multiple parts:

*   [Landmark extraction](landmark-extraction.md)
*   [Data association](data-association.md)

1.  After odometry change (due to robot moving), [state estimation](step-1-odometry-update-prediction-step.md) from odometry
2.  [Update of the estimated state using re-observed landmark data](http://www.evernote.com/shard/s484/nl/217355218/39bdca7c-8c75-420e-a318-fd726f08727e)
3.  [Update landmark database with new landmarks](http://www.evernote.com/shard/s484/nl/217355218/91e0df9b-526e-47e1-af42-65c105fb7f45)

Note: at any point in the three steps on the left, the EKF will have an estimate of the robots current position

![Image.png](./_resources/Basic_EKF_for_SLAM.resources/Image.png)

