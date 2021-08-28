---
title: Filter-based vs optimisation-based SLAM
date: "2020-08-23"
tags:
  - SLAM/filter-vs-optim
  - -sa/processed
---

Parent: [SLAM Index](slam-index.md)

Source: [Scaradozzi 2018 SLAM application in surgery](scaradozzi-2018-slam-application-in-surgery.md)

Main paradigms of SLAM

1.  [Filters](http://www.evernote.com/shard/s484/nl/217355218/48ab2536-eadf-4a7f-8dfa-f377bfbe3839) — [Kalman filters](http://www.evernote.com/shard/s484/nl/217355218/bb893af4-28b5-484b-b110-cdcb4eb91477), Particle filters
2.  Graph-based SLAM
    Estimate the entire trajectory and the map from the full set of measurements (full SLAM)
    

Which SLAM algorithm to use?
Depends on application

*   map resolution
*   update time (real time or not)
*   type of environment
*   type of sensors available

