---
title: Intrinsic vs extrinsic rotations
date: "2021-08-17"
external_url: "http://rock-learning.github.io/pytransform3d/transformation_ambiguities.html"
tags:
  - -sa/processed
  - math/rotations
  - -published
---

**Parent**: [Rotations/SO(3) Group Index](math/rotations/rotations-so3-group-index.md)  
**See also**: [Active/passive or Alibi/alias rotation transformations](math/rotations/active-passive-or-alibi-alias-transformations.md)

**Source**: [http://rock-learning.github.io/pytransform3d/transformation\_ambiguities.html](http://rock-learning.github.io/pytransform3d/transformation_ambiguities.html)

We want to rotate first by $R_1$, then by $R_2$.

## Extrinsic (global) rotation
In global coordinates, extrinsic rotation: $R_2 \cdot R_1$  
![](/_img/extrinsic-rotations.png)

## Intrinsic (local) rotation
In local coordinates, intrinsic rotation: $R_1 \cdot R_2$  
($R_1$ defines new coordinates in which $R_2$ is applied)  
![](/_img/intrinsic-rotations.png)

Specifying the convention is relevant when dealing with Euler angles!!!

## Illustration
**Source**: [bonn-3D-cs](bibliography/bonn-3D-cs.md)

[Active](math/rotations/active-passive-or-alibi-alias-transformations.md) translation --> rotation  
![](/_img/active-transfs-global-local.png)

[Passive](math/rotations/active-passive-or-alibi-alias-transformations.md) translation --> rotation  
![](/_img/passive-transfs-global-local.png)

## Relation
To convert a global rotation to a local rotation, reverse the order of transformations.

e.g.
* Active global transformation A
    * A: first T from origin, followed by R around origin
    * if this were carried out as an equivalent local transformation, the active local transformation would be first R around local CS, then T from local CS  
        ![](/_img/active-local-transf.png)
* Active local transformation B
    * B: first T from local CS, followed by R around local CS
    * if this were carried out as an equivalent global transformation, the active global transformation would be first R around origin, then T from origin  
        ![](/_img/active-global-transf.png)