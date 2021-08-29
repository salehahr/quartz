---
title: Mapping in VIORB
date: "2020-10-20"
tags:
  - -sa/processed
  - SLAM/algos/VIORB
---

Source: [Mur-Artal 2017 VI-ORB](bibliography/mur-artal-2017-vi-orb.md)

Mapping in VIORB
Previously in ORBSLAM (only poses are optimised):
![unknown_filename.png](./_resources/Mapping_in_VIORB.resources/unknown_filename.png)

Now in VIORB, more states to optimise:
![unknown_filename.1.png](./_resources/Mapping_in_VIORB.resources/unknown_filename.1.png)

Increase in complexity

*   more states to optimise (v, b)
*   IMU measurements creates constraints between keyframes

Original ORBSLAM discards redundants KFs (poses a problem with IMU constraints!)
Workaround: in local BA, only allow discarding of KF if, after discarding, the time between two consecutive KFs is short enough (<= 0.5s)
Further: in full BA (after loop closure, or any time for map refinement), only allow time between KFs to be <= 3s (to reduce IMU noise integration)

