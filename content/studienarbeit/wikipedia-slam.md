---
title: Wikipedia SLAM
date: "2020-07-27"
tags:
  - -resources/-bibliography
  - SLAM
  - -resources/-bibliography/bib-to-read
  - -sa/processed
---

Source: [http://en.wikipedia.org/wiki/Simultaneous\_localization\_and\_mapping](http://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping)
Parents: [SLAM Index](SLAM/slam_index.md), [slam-resources](slam-resources.md)

Different types of sensors give rise to different SLAM algorithms whose assumptions are most appropriate to the sensors.

*   At one extreme, visual features provide details of many points within an area --> rendering SLAM unnecessary
    *   shapes in these point clouds can be easily and unambiguously aligned at each step via [image registration](http://en.wikipedia.org/wiki/Image_registration).
*   At the opposite extreme, [tactile sensors](http://en.wikipedia.org/wiki/Tactile_sensor) are extremely sparse
    *   they contain only information about points very close to the agent
    *   require strong prior models to compensate in purely tactile SLAM.
*   Most practical SLAM tasks fall somewhere between these visual and tactile extremes.

Algorithms

*   Statistical techniques
    *   Kalman
    *   Particle/Monte Carlo
*   Set-membership techniques
    *   Bundle adjustment
    *   Maximum a posteriori estimation (MAP) -- SLAM for image data

Given:

*   Controls u
*   Sensor measurements o
*   Time steps t

To estimate:

*   Agent's state x
*   Map of environment m

All quantities are probabilistic.

Objective is to compute:
![c607fe964e04d2d7c46f8420596205eb67737000](http://wikimedia.org/api/rest_v1/media/math/render/svg/c607fe964e04d2d7c46f8420596205eb67737000)

Use Bayes' rule, EM algorithm

Sensor models

*   landmark based
*   raw data based
    *   make no assumption that landmarks can be identified

