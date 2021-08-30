---
title: Lamarca 2020 DefSLAM
date: "2020-08-06"
tags:
  - -resources/-bibliography
  - to-do/go-through-literature-later
  - -resources/-bibliography/bib-read
  - discussion/2020/2020-08
  - -sa/processed
  - discussion/2020/2020-09
  - SLAM/algos/DefSLAM
  - SLAM/deformable
---

URL: <http://arxiv.org/abs/1908.08918>
Authors: Lamarca et al
Code: <http://github.com/UZ-SLAMLab/DefSLAM>
Results (video): [http://www.youtube.com/watch?v=6mmhD2\_t6Gs](http://www.youtube.com/watch?v=6mmhD2_t6Gs)

Summary

*   First monocular SLAM for deformable environments in real-time
    *   Most other SLAM implementations assume rigidity
*   Main techniques used (techniques for monocular non-rigid scenes):
    *   isometric shape from template (SfT)
    *   non-rigid structure from motion (NRSfM)
*   Main principle: computation in [two parallel threads (s. DefSLAM framework)](two-parallel-threads-(s.-defslam-framework).md)
    *   Deformation tracking \[front end\]
    *   Deformation mapping \[back end\]
*   The map from the mapping thread defines the shape-at-rest template used by deformation tracking
*   Validation: compare with ORBSLAM (rigid)
*   Assumes isometric deformation
*   Future work: relocalisation (s. [kidnapped robot problem](kidnapped-robot-problem.md)), loop closure for robustness

Introduction
[Initialisation of monocular SLAM](SLAM/initialisation-of-monocular-slam.md)
Most SLAM algorithms exploit the rigidity assumption!
[NRSfM and SfT](nrsfm-and-sft.md)
[DefSLAM framework](defslam-framework.md)
[DefSLAM and discontinuous areas (classical datasets)](defslam-and-discontinuous-areas-(classical-datasets).md)

Related work
... in visual SLAM

*   Existing deformable visual SLAM
    *   mostly using RGB-D or stereo cameras
    *   the ones mentioned optimise the whole map, but hier DefSLAM only optimises the observed map zone (local zone)
*   Rigid methods used in (semi-)deformable environments
    *   assume negligible deformation
    *   circumvent deformable situations by excluding any deformable regions from the map

... [non-rigid monocular techniques in the literature](non-rigid-monocular-techniques-in-the-literature.md)
In DefSLAM: energy-based SfT and isometric NRSfM are used.

Notation

|     |     |
| --- | --- |
| Map | Set of 3D map points |
| ![unknown_filename.6.png](./_resources/[Lamarca_2020]_DefSLAM.resources/unknown_filename.6.png) | j-th map point in frame t |
| ![unknown_filename.1.png](./_resources/[Lamarca_2020]_DefSLAM.resources/unknown_filename.1.png) | camera pose in frame t |
| ![unknown_filename.2.png](./_resources/[Lamarca_2020]_DefSLAM.resources/unknown_filename.2.png) | surfaced observed in keyframe k |
| ![unknown_filename.3.png](./_resources/[Lamarca_2020]_DefSLAM.resources/unknown_filename.3.png) | template (has map points embedded into it), based initially on keyframe k (deformations can occur after k) -- already explored areas |
| ![unknown_filename.4.png](./_resources/[Lamarca_2020]_DefSLAM.resources/unknown_filename.4.png) | local zone (currently being viewed area) |
| ![unknown_filename.5.png](./_resources/[Lamarca_2020]_DefSLAM.resources/unknown_filename.5.png) | image |
| ![unknown_filename.7.png](./_resources/[Lamarca_2020]_DefSLAM.resources/unknown_filename.7.png) | feature keypoint in image |
| ![unknown_filename.8.png](./_resources/[Lamarca_2020]_DefSLAM.resources/unknown_filename.8.png) | *   warp between the keyframes k and k\*<br>*   image transformation between Ik to Ik\* |
| ![unknown_filename.9.png](./_resources/[Lamarca_2020]_DefSLAM.resources/unknown_filename.9.png) | *   embedding of an image point onto the scene surface<br>*   transforms an image point (2D) into a point on a 3D surface |
| Anchor keyframe \[of a map point\] | *   Keyframe in which a map point is initialised<br>*   After each new KF processing, one of the anchor KFs is selected as the reference KF |
| Reference keyframe | Defines the template used by the deformation tracking |

Tracking
Components: map/template, local zone, camera pose

Stages of tracking:

1.  Data association
2.  Camera pose estimation
3.  Template deformation
4.  New keyframe selection: as soon as mapping finishes one run
    *   If new KF of a new map: this KF becomes an anchor KF, the ref. KF, and a new template is created
    *   If new KF of known region: this KF is a regular KF, the most covisible anchor KF is selected as ref KF, template is refined (deformed)

[Template in DefSLAM](template-in-defslam.md)
[Pinhole camera projection function](pinhole-camera-projection-function.md)
[Tracking optimisation in DefSLAM](tracking-optimisation-in-defslam.md)
[Data association in DefSLAM](data-association-in-defslam.md)

Keyframe selection
A new keyframe is selected when the mapping finishes the last estimation, i.e. new keyframe at the end of each deformation mapping run

Mapping
In a nutshell:

*   recovers observed map as a surface for the next keyframe k
*   the surface Sk is the shape-at-rest of template Tk for the next frames

[Mapping step-by-step in DefSLAM](mapping-step-by-step-in-defslam.md)

*   [NRSfM in DefSLAM](nrsfm-in-defslam.md)
*   [Surface alignment in DefSLAM](surface-alignment-in-defslam.md)
*   [Template substitution in DefSLAM](template-substitution-in-defslam.md)

[Non-Rigid Guided Matching (b/w KFs) in DefSLAM](non-rigid guided-matching-(b_w-kfs)-in-defslam.md)

Validation results
In the experiments, DefSLAM was run sequentially in a single thread (for repeatability)!

![unknown_filename.png](./_resources/[Lamarca_2020]_DefSLAM.resources/unknown_filename.png)

