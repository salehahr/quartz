---
title: Intrinsic vs extrinsic rotations
date: "2021-08-17"
external_url: "http://rock-learning.github.io/pytransform3d/transformation_ambiguities.html"
tags:
  - -sa/processed
  - math/rotations
---

Parent: [Rotations / SO(3) group index](rotations-_-so(3)-group-index.md)
See also: [Active/passive or Alibi/alias rotation transformations](active_passive-or-alibi_alias-rotation-transformations.md)

Source: [http://rock-learning.github.io/pytransform3d/transformation\_ambiguities.html](http://rock-learning.github.io/pytransform3d/transformation_ambiguities.html)

We want to rotate first by R1, then by R2.

In global coordnates, extrinsic rotation:
![unknown_filename.png](./_resources/Intrinsic_vs_extrinsic_rotations.resources/unknown_filename.png)
![unknown_filename.2.png](./_resources/Intrinsic_vs_extrinsic_rotations.resources/unknown_filename.2.png)

In local coordinates, intrinsic rotation:
![unknown_filename.1.png](./_resources/Intrinsic_vs_extrinsic_rotations.resources/unknown_filename.1.png)
(R1 defines new coordinates in which R2 is applied)
![unknown_filename.3.png](./_resources/Intrinsic_vs_extrinsic_rotations.resources/unknown_filename.3.png)

Specifying the convention is relevant when dealing with Euler angles!!!

