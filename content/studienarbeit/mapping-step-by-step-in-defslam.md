---
title: Mapping step-by-step in DefSLAM
date: "2020-11-20"
tags:
  - to-do/to-clarify
  - -sa/processed
  - to-do/missing-link
  - SLAM/algos/DefSLAM
---

Source: [Lamarca 2019 DefSLAM](lamarca-2019-defslam.md)
Parent: [DefSLAM framework](defslam-framework.md)

![unknown_filename.1.png](./_resources/Mapping_step-by-step_in_DefSLAM.resources/unknown_filename.1.png)

Steps

1.  Recover warps between k and k\* (s.  [Non-Rigid Guided Matching (b/w KFs) in DefSLAM](non-rigid guided-matching-(b_w-kfs)-in-defslam.md))
    *   with k: anchor keyframes, i.e. KFs where one of the observed map points was initialised
    *   with k\*: set of best [covisible keyframes](covisible-keyframes.md)
    *   warps: transformation between the images Ik to Ik\*
        *   In DefSLAM, Schwarps (a family of warps using 2D Schwarzian equation regularisers) is used
        *   Schwarps has something to do with the infinitesimal planarity assumption of NRSfM
2.  \[[NRSfM](nrsfm.md)\] Process k\* to get estimate of an up-to-scale surface 
    ![unknown_filename.2.png](./_resources/Mapping_step-by-step_in_DefSLAM.resources/unknown_filename.2.png)
    *   Input of NRSfM: warps
3.  \[[Surface alignment](surface-alignment.md)\] Up-to-scale surface (\\hat{S}\_k) is aligned with the whole map in order to obtained the scaled surface Sk w.r.t. the old map in keyframe k
4.  \[[SfT template substitution](sft-template-substitution.md)\] A new template (mesh with embedded map points) is created from the surface

![unknown_filename.png](./_resources/Mapping_step-by-step_in_DefSLAM.resources/unknown_filename.png)

