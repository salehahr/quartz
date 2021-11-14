---
title: Song 2018 MIS-SLAM
date: "2020-08-24"
tags:
  - -resources/-bibliography
  - -resources/-bibliography/bib-read
  - SLAM/deformable
  - -sa/to-be-processed
---

**Authors**: Song et al

**Note**: referred to in [Lamarca 2020](lamarca-2020.md) as a stereovisual deformable SLAM, uses CPU and GPU, nonlinear optimisation
Video: <http://www.youtube.com/watch?v=2pXokldQBWM>

## Abstract

*   Uses CPU and GPU
*   CPU for ORBSLAM (initial global position)
*   GPU for deformable tracking and dense mapping

## Contents/Chapters

*   Poor localisation of scope in MIS, compared with open surgery
*   Related works mentioned
    *   don't provide a  RT and robust solution for localisation while reconstructing dense deformable surfaces
    *   focus on the monocular scope, fail to solve the problem of missing scale
*   Fast movement
    *   makes visual odometry unstable
    *   causes blurry images
    *   worsens registrations
*   ORB-SLAM proven to be suitable for coupling with dense deformable SLAM

## Initial tracking: ORB-SLAM

*   ORB features and global pose are uploaded to GPU
*   Upload the matched ORB features every time a new observation is made
*   The initial global pose makes the system significantly robuster

## Deformable tracking and dense mapping

*   Receives initial global pose from the CPU
*   Initialises the model with an estimated depth
*   From model: extract potential visible points
*   Project these points onto 2D depth images
*   Registration:
    *   to estimate optimum global pose
    *   to estimate non-rigid warping field
*   Deform the model based on this transformation (registration)
*   Fuse the deformed model with the new observation

Includes in-vivo validation with deformation (Hamlyn datasets)

## Challenges

*   Texture blending
*   Slow optimisation due to large increase in number of nodes
*   Loop closure still needs to be implemented (or improved upon)

## Takeaway

ORB-SLAM seems to be implementable in deformable environment situations

