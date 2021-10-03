---
title: Spike landmarks
date: "2020-07-27"
tags:
  - localisation/landmarks
  - -sa/processed
---

**Source**: [SLAM for Dummies](bibliography/riisgaard-slam-for-dummies.md)

*   Uses extrema to find [landmarks](SLAM/landmarks.md)
*   Find values in the range of a laser scan, where two values differ by more than a certain amount (e.g. 0.5 m)
    *   This finds **big changes in the laser scan**
*   Alternatively, using three values next to each other: $A, B, C$
    *   $(A - B) + (C - B)$ yields a value
    *   Better for finding spikes as it finds actual spikes
*   Rely on the landscape changing a lot between two laser beams
    *   Algo will fail in smooth environments
*   Suitable for indoor environments, however is not robust against envs w/ people
    *   people are picked up as spikes as theoretically they are good landmarks (just not stationary!)

