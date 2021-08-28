---
title: Initialisation of monocular SLAM
date: "2020-11-20"
tags:
  - SLAM/VSLAM
  - -sa/processed
  - SLAM/initialisation
---

Source:  [Lamarca 2019 DefSLAM](lamarca-2019-defslam.md)

Depth information has to be generated before localisation can be performed — how?

*   Capture multiple images which have enough [parallax](parallax.md)
*   These images with parallax allows depth information to be calculated (this uses [motion parallax](motion-parallax.md))
    *   From these images, the map can be generated
    *   Localisation can then be carried out with respect to the map (as long as camera doesn't move off to an unexplored region)

