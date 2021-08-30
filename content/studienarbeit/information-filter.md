---
title: Information Filter
date: "2020-08-23"
tags:
  - to-do/to-clarify
  - -sa/processed
  - filters/kalman-filter
---

Parent: [General Kalman Filter](general-kalman-filter.md)

Source: [Scaradozzi 2018 SLAM application in surgery](studienarbeit/scaradozzi-2018.md)

*   also same assumptions as the [EKF](http://www.evernote.com/shard/s484/nl/217355218/a3417515-123a-4310-ac2f-937cd4878942)
*   main difference: how the Gaussian belief is represented
*   est. cov. — replaced by information matrix (IM)
*   est. state — replaced by information vector (IV)
*   superior to KF in the following ways
    *   data is filtered by summing up the IMs and IVs
    *   often numerically more stable

Dual character of KF and IF

*   in IF: prediction step requires two matrix inversions
    *   higher computational complexity
    *   high-dimension state space
    *   while for KF, update in the prediction step is additive
*   roles are reversed in measurement step

Variants of IF

*   EIF (extended IF)
*   SEIF (sparse extended IF)

Inspired by SLAM filters that are used to represent relative distances

