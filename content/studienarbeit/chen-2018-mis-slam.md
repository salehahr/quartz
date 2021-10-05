---
title: Chen 2018 SLAM-based dense surface reconstruction in MIS with AR
date: "2020-08-24"
tags:
  - to-do/to-clarify
  - -resources/-bibliography
  - -resources/-bibliography/bib-to-read
  - -sa/to-be-processed
---

**Authors** Chen et al

## Abstract

*   Intra-operative dense surface reconstruction framework to provide geometry information from only monocular videos
*   The proposed framework works well with rapid camera movements, however is not suitable for large deformations
*   Only tweaks ORBSLAM to adjust between point density and computational performance

## Contents/Chapters
Problems in medical AR:

*   tissue surface illumination
*   tissue deformation
*   rapid movements of the medical tool e.g. endoscope (s. also [kidnapped robot problem](kidnapped-robot-problem.md) for relocalisation, tracking mus therefore be robust)
*   field of view often very small

"A typical human uses 14 visual cues to perceive depth, only 3/14 are binocular vision related."
s. also: [Monocular depth perception in humans](permanent/10-monocular-depth-perception.md)

Traditional feature-tracking for AR in MIS:

*   SIFT
*   SURF
*   Optical flow tracking
*   Other approaches for soft tissues

However, these are designed for 2D tracking

\--> ORB descriptor

*   binary feature descriptor
*   faster than SURF and SIFT with better accuracy
*   invariant to rotation, illumination and scale

ORB-SLAM uses Bag of Words algo. for relocalisation

Task of the SLAM algo in this framework:

*   Recovers camera POSE
*   Generates a sparse point cloud, based on which 3D geometric information is generated

Inialisation is problematic for monocular SLAM because the depth isn't recoverable from a single image
\--> automatic approach in ORBSLAM:

*   for planar scenes: calculate homography
*   for non-planar scenes: calculate a fundamental matrix dynamically

## Takeaway

Not suitable for large deformations

