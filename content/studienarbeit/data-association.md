---
title: Data association
date: "2020-07-27"
tags:
  - localisation/data-association
  - -sa/processed
---

Parents: [SLAM Index](slam-index.md), [basic-ekf-for-slam](basic-ekf-for-slam.md)

Source: [SLAM for Dummies](slam-for-dummies.md)
Backlinks: [What is SLAM?](what is slam_.md), [data association in defslam](data association in defslam.md), [visual slam-implementation-framework](visual-slam-implementation-framework.md)

Matching observed landmarks from different scans (different time steps) with each other.
Also called 're-observing' landmarks.

Problems that can arise:

*   The landmark(s) might not be observed every time step (bad landmark)
*   Something might be observed as a landmark, but it never appears again (bad landmark)
*   Wrong association of a landmark to a previously seen landmark

Goal: define a suitable data-association policy to minimise the first two problems
Given: database that stores previously seen landmarks (initially empty)
As a rule: a landmark is only considered worthwhile to be used in SLAM once it is seen N times

Data association policies

*   [Nearest Neighbour](nearest-neighbour.md)

