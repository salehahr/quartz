---
title: NRSfM and SfT
date: "2020-11-20"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
  - SLAM/deformable-SLAM
---

**Source**: [Lamarca 2019 DefSLAM](lamarca-2019-defslam.md)

In literature, non-rigid monocular scenes are handled by NRSfM and SfT

NRSfM (non-rigid structure from motion)

*   batch processing of images to recover deformation
*   computationally demanding — slower than SFT

SFT (shape from template)

*   uses only a single image — faster than NRFfM
*   lower computational cost
*   must have a known 3D template (textured model)

