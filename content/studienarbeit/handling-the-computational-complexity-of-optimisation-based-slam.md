---
title: Handling the computational complexity of optimisation-based SLAM
date: "2020-11-17"
tags:
  - SLAM/filter-vs-optim/opt-based
  - -sa/processed
---

**Parent**: [SLAM Index](slam-index.md)
**Source:** [Forster 2017 IMU Preintegration](forster-2017-imu-preintegration.md)

Complexity of nonlinear batch optimisation

*   The trajectory and the map, which comprise the states, grow with time
*   The larger the SLAM problem, the less feasible it is to perform the optimisation in real-time

Solutions to improve computational efficiency

*   Keyframe-based methods: discard frames except for a few selected keyframes
*   Run the optimisation parallelly (e.g. tracking and mapping threads)
*   Fixed-lag smoothing: Use of a local map of fixed size, with marginalisation of the old states (summarise the old states into a prior term)
    *   Filtering is a special case of this: window of size 1, i.e. only the latest sensor state is optimised
    *   \[-\] commits to a linearisation point when marginalising
    *   linearisation errors will eventually accumulate, can lead to drift or other inconsistencies
*   Incremental smoothing
    *   In between filtering and batch optimisation
    *   Usage of factor graphs
    *   Identifies and updates only a small subset of variables affected by a new measurement ("new constraint?")

