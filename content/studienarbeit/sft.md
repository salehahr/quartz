---
title: Shape from Motion
date: "2020-11-20"
tags:
  - to-do/go-through-literature-later
  - SLAM/deformable-SLAM
  - to-do/not-good-enough
  - -sa/to-be-processed
  - -published
---


Initial paper?: https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7010934https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7010934

## Goal
reconstruct the surface of an object
* reference 3D shape (template) of the object is available
* under a specific deformation constraint

---

**Source**: [lamarca-2020](studienarbeit/lamarca-2020.md)

## SFT (shape from template)

*   uses only a single image — faster than [nrsfm](studienarbeit/nrsfm.md)
*   lower computational cost
*   must have a known 3D template (textured model)

### SfT methods
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