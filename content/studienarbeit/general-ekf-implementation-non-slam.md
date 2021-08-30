---
title: General EKF implementation (non-SLAM)
date: "2020-08-22"
tags:
  - filters/EKF
  - -sa/processed
---

Parent: [Extended Kalman Filter](SLAM/extended-kalman-filter.md)

Source: [SLAM for Dummies](slam-for-dummies.md)
General (non-SLAM) implementation of EKF:

*   only state estimation
*   robot is given a perfect map
*   no map update necessary

SLAM implementations of EKF requires map update and therefore the matrices are changed.

Source: [Scaradozzi 2018 SLAM application in surgery](studienarbeit/scaradozzi-2018.md)
EKF [vs KF](http://www.evernote.com/shard/s484/nl/217355218/bb893af4-28b5-484b-b110-cdcb4eb91477)

*   circumvents linearity assumption
*   uses nonlinear functions to describe
    *   the next state probability
    *   measurement probability
*   approximates the state distribution with a Gaussian Random Variable

