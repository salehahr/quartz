---
title: Intrinsic vs extrinsic rotations
date: "2021-08-17"
external_url: "http://rock-learning.github.io/pytransform3d/transformation_ambiguities.html"
tags:
  - -sa/processed
  - math/rotations
  - -published
---

**Parent**: [Rotations/SO(3) Group Index](rotations/rotations-so3-group-index.md)  
**See also**: [Active/passive or Alibi/alias rotation transformations](rotations/active-passive-or-alibi-alias-rotation-transformations.md)

**Source**: [http://rock-learning.github.io/pytransform3d/transformation\_ambiguities.html](http://rock-learning.github.io/pytransform3d/transformation_ambiguities.html)

We want to rotate first by $R_1$, then by $R_2$.

## Extrinsic rotation
In global coordinates, extrinsic rotation: $R_2 \cdot R_1$  
![unknown_filename.2.png](studienarbeit/_resources/Intrinsic_vs_extrinsic_rotations.resources/unknown_filename.2.png)

## Intrinsic rotation
In local coordinates, intrinsic rotation: $R_1 \cdot R_2$  
($R_1$ defines new coordinates in which $R_2$ is applied)  
![unknown_filename.3.png](studienarbeit/_resources/Intrinsic_vs_extrinsic_rotations.resources/unknown_filename.3.png)

Specifying the convention is relevant when dealing with Euler angles!!!
