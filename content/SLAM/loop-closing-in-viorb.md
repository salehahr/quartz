---
title: Loop closing in VIORB
date: "2020-10-20"
tags:
  - SLAM/loop-detection
  - SLAM/algos/VIORB
  - -sa/processed
---

**Source**: [Mur-Artal 2017 VI-ORB](bibliography/mur-artal-2017-vi-orb.md)  
**See also**: [Loop closure detection (general)](SLAM/loop-closure-detection.md)

## Overview

*   To reduce drift accumulated during exploration (when returning to an already mapped location)
*   Loop detection: of large loops using place recognition
*   Loop correction: first do lightweight pose-graph optimisation (PGO), then do full BA in a separate thread (in order not to interfere with real-time operations)

## Implementation

*   After loop detection: do match validation (alignment of points between keyframes)
*   Then pose-graph optimisation to reduce the accumulated error in trajectory
    *   (PGO: pose-only, ignores IMU info)
    *   IMU info ignored, but velocities are corrected by rotating them according to keyframe orientation --> suboptimal, but should be accurate enough to allow IMU data to be used right after the PGO
    *   in ORBSLAM: PGO is 7-DoF optimisation (due to scale + 3 rot + 3 xyz)
    *   in VIORB, 6 DoF (scale is known from initialisation bzw. observable)

