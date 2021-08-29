---
title: Tracking in VIORB
date: "2020-10-20"
tags:
  - to-do/missing-tag
  - SLAM/algos/VIORB
  - -sa/to-be-processed
---

**Source**: [Mur-Artal 2017 VI-ORB](bibliography/mur-artal-2017-vi-orb.md)

Tracking in VIORB

*   Visual-inertial tracking at frame rate, instead of using an ad-hoc motion model as in the original ORB-SLAM
*   Tracked states: \[sensor pose (R, p), velocities v, biases b\]
*   Once the camera pose is predicted, map points are projected, then matches with existing features on the frame
*   Then optimise the current frame j, depending on whether
    *   the map has just been updated
    *   the map is unchanged

Here, the optimisation function for tracking (when map unchanged) is:
![unknown_filename.1.png](./_resources/Tracking_in_VIORB.resources/unknown_filename.1.png)
![unknown_filename.png](./_resources/Tracking_in_VIORB.resources/unknown_filename.png)

