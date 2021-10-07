---
title: Tracking optimisation in DefSLAM
date: "2020-11-20"
tags:
  - to-do/to-clarify
  - -sa/processed
  - SLAM/algos/DefSLAM
---

**Source**: [lamarca-2020](studienarbeit/lamarca-2020.md)

## Optimisation function
*   Minimises
    *   reprojection error (in the image)
    *   deformation energy (of the template)
    *   boundary nodes of the local zone are fixed (i.e. not set as arguments to the optimisation function)
        *   this makes the absolute camera pose observable [ ] how?
        *   in order to constrain the gauge freedoms
*   Initial guess: values from previous optimisation (i.e. previous frame: t-1)

![unknown_filename.1.png](./_resources/Tracking_optimisation_in_DefSLAM.resources/unknown_filename.1.png)

### Reprojection error
![unknown_filename.png](./_resources/Tracking_optimisation_in_DefSLAM.resources/unknown_filename.png)
robust against outliers due to Huber robust kernel

### Deformation energy
Deformation energy = stretching energy + bending energy + temporal term
![unknown_filename.2.png](./_resources/Tracking_optimisation_in_DefSLAM.resources/unknown_filename.2.png)

*   "involves two spatial and one temporal constraint"
*   requires the derivatives of each term/regulariser
*   stretching energy: change in edge lengths in the local zone (w.r.t. shape at rest)
    ![unknown_filename.5.png](./_resources/Tracking_optimisation_in_DefSLAM.resources/unknown_filename.5.png)
    
*   bending energy: change in node mean curvatures (w.r.t. shape at rest)
    *   Node mean curvature: estimated using the discrete Laplacian operator
        ![unknown_filename.4.png](./_resources/Tracking_optimisation_in_DefSLAM.resources/unknown_filename.4.png)
        
*   temporal term/reference regulariser: smoothness between estimates
    *   to prevent abrupt changes between frames
    *   to keep the template as close as possible to its initial position
        ![unknown_filename.3.png](./_resources/Tracking_optimisation_in_DefSLAM.resources/unknown_filename.3.png)

