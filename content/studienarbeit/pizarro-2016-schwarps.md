---
title: Pizarro 2016 Schwarps
date: "2020-12-20"
tags:
  - to-do/to-clarify
  - -resources/-bibliography
  - -resources/-bibliography/bib-to-read
  - -sa/processed
  - SLAM/algos/DefSLAM
---

**Author**: Daniel Pizarro et al.

**Abstract**

*   Warp between two images of a deforming surface:
    *   a transformation that depict the geometric deformation between the two
    *   'maps points between images of a deforming surface'
*   Current approach to enforce a warp's smoothness: penalise its second order partial derivatives
    *   However this favours locally affine warps
    *   Does not capture the local projective component of the image deformation
*   Propose: **novel penalty to smooth the warp while capturing the deformation's local projective structure**
    *   Proposed penalty is based on equivalents to the Schwarzian derivatives
        *   Schwarzian derivatives: projective differential invariants exactly preserved by homographies
    *   Methodology to derive a set of PDEs with only homographies as the solutions
*   Validation: Schwarps outperform existing warps in modeling and extrapolation power: perform better in deformable reconstruction methods

**Introduction/Related work**

*   Projective geometry: study of the geometric properties of projective transformations
    *   Uses in CV: image stitching, image registration, SfM (which all assume rigid scenes)
    *   The above are insufficient forfor problems like NRSfM, SfT and non-rigid image registration
*   In a deformable environment, one of the big problems is the modeling of the image warp
*   Representation of a warp: generally via linear basis expansion (but there are also other warp models)
    *   e.g. Thin-Plate Spline (TPS), tensor-product BSpline (BS), finite elements, etc.
*   Fitting a warp to measurements made requires priors
    *   \`Registration measurements are discrete and generally scattered in the image'
    *   General assumption: warp is smooth or piecewise smooth
*   Current approach to enforce a warp's smoothness: penalise its derivatives
    *   penalising second order derivatives leads to **bending energy**; this forces the warp to be locally affine
        *   BE = 0 implies warp is a global affine transformation
        *   this ignores a fundamental prior that images are formed by perspective projection of surfaces
            *   implies that the warp is a rational function whose derivatives _do not vanish at any order_
            *   hence, using the BE penalty causes the infinitesimal projective information [ ] of the warp to be discarded
            *   affects methods that require high accuracy in the warp's derivatives, such as NRSfM and SfT
*   Thus, we need to find another penalty
    *   Penalties that force the warp to behave locally as a homography
        *   Led to Generalised TPS warps, NURBS warp, which used 3D bending energy expressed in homogeneous coordinates
    *   Using local homographies to explicitly model the warp — has limitations ...
    *   Proposed penalty: able to smooth a warp while capturing the infinitesimal projective structure
        *   applicable to all warp models (including linear basis expansions; does not require the use of rational warps)
            *   Rational warps, in theory, are smooth and capture IP structure
            *   However, they are non-convex and may be unstable due to their rational structure
        *   based on projective differential geometry (PDG) --> Schwarzian derivative

**Contributions**

1.  New derivation framework for 1D Schwarzian derivative which extends to higher dimensions (we want 2D, for images)
2.  Schwarp: image warp which is estimated while penalising the residual of the 2D Schwarzian equations

