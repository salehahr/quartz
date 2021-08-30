---
title: DefSLAM and discontinuous areas (classical datasets)
date: "2021-01-15"
external_url: "http://github.com/UZ-SLAMLab/DefSLAM/issues/1"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
---

**Parent**: [Lamarca 2020 DefSLAM](studienarbeit/lamarca-2020.md)
**Source**: <http://github.com/UZ-SLAMLab/DefSLAM/issues/1>

JoseLamarca:
DefSLAM is suitable for rigid areas, proof of that is the abdominal sequence that is kind of rigid.
The problem for these sequences is the discontinuous areas. For the monocular case, we are assuming that the surface is smooth that is not usually valid for the classical datasets. Apart from complexity issues that algorithms with RGB-D and stereo cameras could have in those scenes \[1\] and \[2\].

In our decision to choose an algorithm for the mapping, there are two main state-of-the-art non-rigid reconstruction approaches:

1.  going for orthogonal cameras and assuming that you can see the real size of the object in your image (there are a vast of good works in the literature, very recommended \[3\])
2.  going for perspective cameras and impose isometry or inextensibility.

We decide to go for perspective cameras due to the nature of our scenarios with strong perspective effects.

The problem using perspective cameras appears when you try to reconstruct independently each point in a non-rigid environment, you always have gauge freedom in the scale for each point, i.e. you can track a small fly very close to the camera or a large elephant further away having exactly the same measurements in the camera. Without any restrictions, It would be equivalent to do a SLAM independently for every single point, so you have to constrain them in some way.

What you can estimate independently of this effect is the normals of the points assuming isometry \[3,4\] (in the paper \[2\] sec. 5.B). That is why you have to impose a regularization to recover the depth. Following the work of Shaifali in \[3\] and Chhatkuli in \[4\], we estimate the surface by imposing minimum bending that is a kind of a minimal surface.

In our case, working inside the body it is a valid assumption for many cases of laparoscopies like the ones presented in the Hamlyn dataset.
In contrast, assuming that the points are connected by a smooth surface does not fit with the scenes in the classical datasets like EuroC or TUM at least that you follow a single object. To generalize monocular deformable SLAM in those scenes, we should find another regularization.

This papers should be enough for a smooth introduction to deformable reconstruction:

\[1\]R. A. Newcombe, D. Fox, and S. M. Seitz. Dynamicfusion: Reconstruction and tracking of non-rigid scenes in real-time. In CVPR, 2015.
\[2\] J. Song, J. Wang, L. Zhao, S. Huang, and G. Dissanayake. Misslam: Real-time large-scale dense deformable slam system in minimally invasive surgery based on heterogeneous computing.
\[1\] Dai, Yuchao, Hongdong Li, and Mingyi He. "A simple prior-free method for non-rigid structure-from-motion factorization."
\[2\] "Defslam: Tracking and mapping of deforming scenes from monocular sequences"
\[3\] S. Parashar, D. Pizarro, and A. Bartoli. Isometric non-rigid shape-from motion with Riemannian geometry solved in linear time.
\[4\] A. Chhatkuli, D. Pizarro, and A. Bartoli. Non-rigid shape-from-motion for isometric surfaces using infinitesimal planarity.

