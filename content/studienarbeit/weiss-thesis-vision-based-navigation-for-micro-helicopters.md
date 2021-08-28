---
title: (Weiss Thesis) Vision based navigation for micro helicopters
date: "2021-04-25"
tags:
  - -resources/-bibliography
  - -resources/-bibliography/bib-skimmed
  - -sa/to-be-processed
---

Source
Backlinks

Authors Stephan Weiss
Abstract

*   Issues that arise during state estimation and sensor self-calibration
*   Application area: large and unknown areas, micro helicopter
*   Vision based method used uses SfM, is compares mapless and map-based methods
*   Statistical and modular sensor fusion strategy
    *   recovery of pose and drifts
    *   modular: camera as a black box sensor, allows other sensors additionally
*   Observability analysis

Literature review

*   Fusing IMU with monocular vision: given [extrinsic parameters](extrinsic parameters.md), an IMU is able to recover metric scale, as well as help transition across short vision failure period
*   Armesto et al. uses loose coupling: compares EKF with UKF, says UKF is more accurate but EKF is computationally cheaper/faster.
*   (Mirzaei and Roumeliotis (2008)) and (Kelly and Sukhatme (2011)) KF-based calibration

Contents/Chapters
Takeaway

