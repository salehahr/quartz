---
title: Multisensor fusion
date: "2020-07-30"
tags:
  - SLAM/multisensor-SLAM
  - sensors
  - -sa/processed
---

Parent: [SLAM Index](slam-index.md), [geometric-metric-slam](geometric-metric-slam.md)

Source: [Cometlabs What You Need to Know About SLAM](cometlabs what you-need-to-know-about-slam.md)

*   Avoid limitations of using only one sensor
    *   Relative measurements: provide precise positioning information constantly
    *   At certain times absolute measurements are made to correct potential errors (correct drift)
*   several approaches (for localisation), e.g.
    *   merge sensor feeds at the lowest level before being processed homogeneously
    *   hierarchical approaches (fuse state estimates derived independently from multiple sensors)
    *   s. also [loose vs tight coupling](loose-vs-tight-coupling.md)
*   combine pos measurements in a formal probabilistic framework (e.g. Markov Localisation Framework)
    *   localisation problem consists of estimating the probability density over the space of all locations
    *   MLF: combines info from sensors to form a combined belief in location

Source: [Wu 2018 Image-based camera localization: an overview](wu 2018-image-based-camera-localization_-an-overview.md)

*   recently, vision and IMU fusion has attracted attention 
*   universality and complementarity of visual-inertial sensors(s. [why use the visual-inertial sensor combination?](why-use-the-visual-inertial-sensor-combination_.md))
*   main distinctions: [loose vs tight coupling](loose-vs-tight-coupling.md)

