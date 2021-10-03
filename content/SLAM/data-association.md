---
title: Data association
date: "2020-07-27"
tags:
  - localisation/data-association
  - -sa/processed
  - -published
---

**Source**: [SLAM for Dummies](bibliography/riisgaard-slam-for-dummies.md)  

Matching observed [landmarks](SLAM/landmarks.md) from different scans (different time steps) with each other.
Also called 're-observing' landmarks.

## Problems that can arise

*   The landmark(s) might not be observed every time step (bad landmark)
*   Something might be observed as a landmark, but it never appears again (bad landmark)
*   Wrong association of a landmark to a previously seen landmark

## Goal
Define a suitable data-association policy to minimise the first two problems

* Given: database that stores previously seen landmarks (initially empty)
* As a rule: a landmark is only considered worthwhile to be used in SLAM once it is seen N times

## Data association policies
e.g. [Nearest Neighbour](SLAM/nearest-neighbour.md)

