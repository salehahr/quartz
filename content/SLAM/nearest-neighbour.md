---
title: Nearest Neighbour
date: "2020-08-06"
tags:
  - localisation/data-association
  - -sa/processed
---

**Source**: [SLAM for Dummies](bibliography/riisgaard-slam-for-dummies.md)

Nearest neighbour approach

1.  Get a new laser scan --> ([landmark extraction](SLAM/landmark-extraction.md)) extract all visible landmarks
2.  Associate each extracted LM to the [closest LM](SLAM/distance-between-landmarks.md) we have seen more than $N$ times
3.  Pass each pairs of association (extracted LM, LM in database) through a [validation gate](SLAM/validation-gate.md)
    1.  If pair passes --> $n = n + 1$ (num. times seen)
    2.  If pair fails --> add new LM to database, with $n := 1$

