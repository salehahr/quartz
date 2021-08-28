---
title: (Mur-Artal 2017) VI-ORB
date: "2020-10-20"
tags:
  - -resources/-bibliography
  - to-do/go-through-literature-later
  - -resources/-bibliography/bib-read
  - -sa/processed
  - discussion/2020/2020-10
  - SLAM/algos/VIORB
---

Backlinks: [Chen 2018 Review of VI SLAM](chen-2018-review.md), [keyframe-based tightly-coupled multisensor slam](keyframe-based tightly-coupled multisensor slam.md), [todo](todo.md), [works of-possible-interest](works-of-possible-interest.md)

URL: <http://ieeexplore.ieee.org/abstract/document/7817784>,
Authors: Mur-Artal, Tardós
Code: <http://paperswithcode.com/paper/visual-inertial-monocular-slam-with-map-reuse>
Results (video): <http://www.youtube.com/watch?v=JXRCSovuxbA>

Abstract

*   current VI odometry approaches: drift accumulates due to lack of loop closure
*   therefore there is a need for tightly-coupled VI-SLAM with loop closure and map reuse
*   here: focus on monocular case, but applicable to other camera configurations
*   builds on ORB-SLAM (from same author)
*   IMU initialisation method (initialises: scale, gravity direction, velocities, gyroscope bias, accelerometer bias) depends on visual monocular initialisation (coupled initialisation)

Other works: recent tightly-coupled VIO (both filtering- and optimisation-based) lack loop closure, so drift accumulates

Introduction
[Why use the visual-inertial sensor combination?](http://www.evernote.com/shard/s484/nl/217355218/c58f0d77-f8d7-4bd8-b7e3-ae81cdcfa066)

*   Camera: [Pinhole camera projection function](pinhole-camera-projection-function.md)
*   [IMU](imu.md) (frame notation:-b): [states,-dynamics-equations](states,-dynamics-equations.md)
*   Rigid transformation between camera and IMU ![unknown_filename.png](./_resources/[Mur-Artal_2017]_VI-ORB.resources/unknown_filename.png)

Framework of VI-ORB

3 parallel threads

1.  \[Front end\] [Tracking](http://www.evernote.com/shard/s484/nl/217355218/56968e4d-e330-468b-99d6-bf0a0945cc64)
    Tracking via optimisation of the current frame, assuming a fixed map (unchanged map)
    
2.  \[Back end\] [Local mapping](http://www.evernote.com/shard/s484/nl/217355218/ffa53026-7934-4309-951a-dc3e2c29b7c6)
    *   local BA over several keyframes (sliding window)
    *   this local BA is a compromise between
        *   full smoothing (over all keyframes) — high computational complexity
        *   marginalising out past keyframes (loss of information)
3.  [Loop closure](http://www.evernote.com/shard/s484/nl/217355218/ad1c21c2-5886-4b59-9385-e2506d41bedd)

Initialisation

*   Need for a reliable VI initialisation that provides accurate state estimate
*   Because both the tracking (front end) and BA (back end) fix the states in their optimisations, this can bias the solution --> need for initialisation [x] fix states?: states which aren't the argument of the optimisation function, i.e. fixed (not optimised)
*   Optimal solution for initialisation of all the required init. variables \[scale, gravity, biases, velocities, structure of the opt. graph, camera pose\] would require a full BA,
    *   however this is split into smaller steps
*   The proposed initialisation is general and applicable to any keyframe-based monocular SLAM
*   Requirement: any two consecutive keyframes must be close in time (to reduce IMU noise integration)

1.  Process the first few seconds of video with visual monocular SLAM (here using ORBSLAM)
    *   This gets the structure estimate as well as several keyframe poses scaled by an unknown scale
    *   Use a motion that makes all variables observable
2.  Compute gravity bias from orientation of keyframes
3.  Initial guess for scale, accelerometer bias (using known magnitude of gravity 9.81 m/s2)
4.  Refine the scale and gravity direction
5.  Get velocities for all keyframes

When reinitialising after relocalisation (after a long time; using place recognition):

*   Reinitialise bg gyrometer bias
*   Scale s and gravity g already known from first initialisation, so no need to calculate anew
*   Estimate ba accelerometer bias from the same equation used during initialisation (simplified now due to knowledge of s, g)

