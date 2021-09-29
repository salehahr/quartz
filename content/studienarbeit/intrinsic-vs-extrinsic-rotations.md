---
title: Intrinsic vs extrinsic rotations
date: "2021-08-17"
external_url: "http://rock-learning.github.io/pytransform3d/transformation_ambiguities.html"
tags:
  - -sa/processed
  - math/rotations
---

**Parent**: [Rotations/SO(3) Group Index](studienarbeit/rotations-so-3-group-index.md)  
**See also**: [Active/passive or Alibi/alias rotation transformations](studienarbeit/active-passive-or-alibi-alias-rotation-transformations.md)

**Source**: [http://rock-learning.github.io/pytransform3d/transformation\_ambiguities.html](http://rock-learning.github.io/pytransform3d/transformation_ambiguities.html)

We want to rotate first by $R_1$, then by $R_2$.

In global coordinates, extrinsic rotation: $R_2 \cdot R_1$  
![unknown_filename.2.png](./_resources/Intrinsic_vs_extrinsic_rotations.resources/unknown_filename.2.png)

In local coordinates, intrinsic rotation: $R_1 \cdot R_2$  
($R_1$ defines new coordinates in which $R_2$ is applied)  
![unknown_filename.3.png](./_resources/Intrinsic_vs_extrinsic_rotations.resources/unknown_filename.3.png)

Specifying the convention is relevant when dealing with Euler angles!!!

