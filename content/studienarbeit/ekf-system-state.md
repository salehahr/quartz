---
title: EKF System State
date: "2020-08-06"
tags:
  - filters/EKF
  - -sa/processed
---

Source: [SLAM for Dummies](slam-for-dummies.md)
Backlinks:  [EKF matrices](ekf-matrices.md), [step-2:-re-observation](step-2-re-observation.md)

*   Contains robot POSE and landmark position
*   POSE: (x y theta)\_r
*   LM: (x, y)\_l1 ... (x,y)\_ln; n = num. of landmarks
*   Size: 3+2n rows

