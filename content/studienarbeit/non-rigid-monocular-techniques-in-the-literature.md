---
title: Non-rigid monocular techniques in the literature
date: "2020-11-20"
tags:
  - to-do/go-through-literature-later
  - SLAM/deformable-SLAM
  - to-do/not-good-enough
  - -sa/to-be-processed
---

Source: [Lamarca 2019 DefSLAM](lamarca-2019-defslam.md)

SfT methods

*   require:
    *   1 monocular image
    *   1 textured shape at rest (template) "geometry" as the deformation model
*   different definitions of the deformation model
    *   analytic, e.g. isometric deformation-based: assumes preserved geodesic distance between surface points
        *   isometry for SfT has proven to be well-posed --> led to stable, real-time solutions
    *   energy-based; jointly minimises {energy shape w.r.t. template \[shape at rest\] + reprojection error for image correspondences}
*   classification according to \[[http://www.cv-foundation.org/openaccess/content\_cvpr\_2015/papers/Gallardo\_Shape-From-Template\_in\_Flatland\_2015\_CVPR\_paper.pdf](http://www.cv-foundation.org/openaccess/content_cvpr_2015/papers/Gallardo_Shape-From-Template_in_Flatland_2015_CVPR_paper.pdf)\]
    *   statistics-based
        *   use data to learn the space of deformations
        *   effective in low-dimensional spaces
    *   physics-based
        *   uses mathematical models (based on physical laws) in order to compute the space of deformations
        *   e.g. isometric model

Orthographic NRSfM

*   usually fails with very large deformations
*   uses an orthographic camera projection/model
*   (weak approximation to the perspective camera) — a limitation, as many vision-related applications have a significant perspective effect
*   exploits
    *   spatial constraints
    *   temporal constraints
    *   spatiotemporal constraints
*   usually ok for small deformations, but not for very large deformations

Perspective NRSfM

*   the perspective camera model is more accurate than the orthographic one
*   also uses the isometry assumption (as in SfT methods), which has produced good results in NRSfM
*   Parashar 2018 "Isometric NRSfM" \[6\] local method that handles occlusions and missing data well

In DefSLAM: energy-based SfT and isometric NRSfM are used.

