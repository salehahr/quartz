---
title: Non-Rigid Guided Matching (b/w KFs) in DefSLAM
date: "2020-11-25"
tags:
  - to-do/to-clarify
  - -sa/processed
  - SLAM/algos/DefSLAM
---

Source: [Lamarca 2019 DefSLAM](lamarca-2019-defslam.md)
**Backlinks**: [NRSfM in DefSLAM](nrsfm-in-defslam.md)

*   Matching between keyframes (used in deformation mapping in DefSLAM)

*   Use an estimated warp as a reference
    *   To increase number of matches in the covisible keyframes

**Process**

1.  Matches are given by deformation tracking
2.  Estimate an initial warp between k and k\* (covisible keyframes) [ ] how?
3.  Using this initial warp, estimate where a point would be seen in k\*
4.  Define a search region around thesse estimated positions. The search regions may contain several keypoints
5.  Select the keypoint with the smallest distance between the ORB descriptors (criterion: Hamming distance, apply threshold) --> these are the new matches
6.  Add them to the initial matches and estimate the final warp

