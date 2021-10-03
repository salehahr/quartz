---
title: Loop closure detection
date: "2020-08-03"
tags:
  - -sa/processed
  - SLAM/loop-detection
  - -published
---

**Source**: [cometlabs](bibliography/cometlabs.md)   
**See also**: [loop-closing-in-viorb](SLAM/loop-closing-in-viorb.md)


## Loop closure
*   Process of observing the same scene by non-adjacent frames and adding a constraint (relationship? association?) between them
*   A long-term data association in the [VSLAM Framework](SLAM/vslam-framework.md) (part of front end)
*   Sort of incorporates [topological SLAM](topological-slam.md) into metric SLAM

![loop-closure](_img/loop-closure.png)

## Importance

*   Final refinement step (in data association)
*   Important for obtaining a globally consistent SLAM solution, especially when optimising over a long period of time

## Basic loop closure detection
Match the current frame to all previous frames using feature matching

*   Computationally expensive, not always suitable for real-time applications
*   For RT—a possible solution: Define [key frames](SLAM/keyframes-in-loop-closure-detection.md) and perform the comparison with only the key frames

## Problems with loop closure

*   False positive/perceptual aliasing: Places are different, but are perceived as the same
*   False negative: Places are the same, but perceived as being different
*   Abhilfe: [precision recall curve](precision-recall-curve.md)

