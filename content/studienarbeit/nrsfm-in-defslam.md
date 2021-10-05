---
title: NRSfM in DefSLAM
date: "2020-11-20"
tags:
  - to-do/to-clarify
  - -sa/processed
  - to-do/missing-link
  - SLAM/algos/DefSLAM
  - -published
---

**Parent**: [Mapping step-by-step in DefSLAM](mapping-step-by-step-in-defslam.md)
**Source**: [lamarca-2020](studienarbeit/lamarca-2020.md)

**See also**: [NRSfM](studienarbeit/nrsfm.md)

## Assumptions

*   Isometric deformation
*   Infinitesimal planarity \[DEF\]: any surface can be approximated as a plane at infinitesimal level, all the while maintaining its curvature at a global level

## Locality
The method used here is a local method --> implies that it handles missing data and occlusions inherently

*   surface deformation is modelled locally for each point, under the above assumptions

## Embedding, $\phi_k$ of the scene surface

*   is a parametrisation — transforms an image point to a point on a 3D surface
*   uses the normalised coordinates of the image Ik (xhat, yhat)

|     |
| --- |
| ![unknown_filename.png](./_resources/NRSfM_in_DefSLAM.resources/unknown_filename.png) |
| ![unknown_filename.1.png](./_resources/NRSfM_in_DefSLAM.resources/unknown_filename.1.png) |
| ![Image.png](./_resources/NRSfM_in_DefSLAM.resources/Image.png) |

## Procedure

1.  A point is matched in more than two keyframes (warps are used in the [matching process](matching-process.md))
    *   We can calculate its normal in its anchor keyframe k
    *   The normal is defined by the variables K below
2.  Perform nonlinear optimisation to recover the variables K (which appear in the vector of the normal to surface)
    ![unknown_filename.2.png](./_resources/NRSfM_in_DefSLAM.resources/unknown_filename.2.png)
    *   P and Q are cubic polynomial equations that are derived from the metric tensors and Christoffel symbols of Sk and Sk\*
    *   P and Q contain p and q coefficients which depend on
        *   normalised coordinates
        *   1st order derivative of warp
        *   2nd order derivative of warp
    *   Initial solution: normals of the deformed template 
        ![unknown_filename.3.png](./_resources/NRSfM_in_DefSLAM.resources/unknown_filename.3.png)
         when the keyframe k was inserted
        
3.  Calculate normal, nj to surface for all points j in last keyframe k
4.  Get an initial surface from the normals (SfN: shape from normals)
    *   model the initial surface as a bicubic spline (like a spline in 3D)
    *   the spline is parametrised by its control nodes depth
5.  Fit node depth to get a surface orthogonal to the estimated normals; use a regulariser in terms of bending energy
6.  The final depth estimation is then up-to-scale
    *   the embedding $\phi_k$
    *   the up-to-scale surface 
        ![Image.1.png](./_resources/NRSfM_in_DefSLAM.resources/Image.1.png)
        

## NRSfM math
![unknown_filename.4.png](./_resources/NRSfM_in_DefSLAM.resources/unknown_filename.4.png)

