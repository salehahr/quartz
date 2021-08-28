---
title: Besprechung 2021-03-08
date: "2021-03-08"
tags:
  - -sa/processed
  - discussion/2021/2021-03
---

Agenda

*   DefSLAM + OS3
    *   Up till DefTracking::MonocularInitialization()
    *   on hold, working on Kalman stuff for the time being
*   DefSLAM + Kalman
    *   new plot (monocular trajectory without any pose updating)
    *   [ ] to do: use noisy stereo data, plug into update step while discarding images
    *   functions in System.cc: read data, update pose
*   DefSLAM + sockets

* * *

Meeting notes:

*   next step: implement the Kalman filter. When that is done, discuss next steps e.g. how to test/validate
    - [ ] KIV: Mon 15.03.2021
    *   try model-free Kalman filter with random walk (xnext = I\*x + noise)
*   discussed, but out of scope for the moment: outsource the optimisation e.g. to Python/MATLAB, then feed the results back into DefSLAM
*   we are getting a new Linux laptop
*   if there is time: interface/bindings for reading/writing input into DefSLAM
*   new narrative for SA presentation: worked on Kalman filter, then worked on trying to incorporate an optimisation-based SLAM
*   sockets with C++ as a Hiwi task maybe

