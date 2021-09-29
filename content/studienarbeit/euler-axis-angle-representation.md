---
title: Euler axis/angle representation
date: "2021-08-17"
tags:
  - -sa/processed
  - math/rotations
---

Parents: [Rotations / SO(3) group index](rotations _ so(3)-group-index.md), [orientation-parametrisations](orientation-parametrisations.md)  
See also: [Rotation vector representation](rotation-vector-representation.md)  
**Backlinks**: [Gibbs / Rodrigues parameter representation for rotations](gibbs _-rodrigues-parameter-representation-for-rotations.md)

Source: [Markley 2014](markley-2014.md)

3 parameters:

*   there appears to be 4: 1 angle, 3-component unit vector (Euler axis, Euler angle of the rotation)
*   however, the vector e is a unit vector (constrained by ![unknown_filename.6.png](./_resources/Euler_axis_angle_representation.resources/unknown_filename.6.png))

To rotation matrix
![unknown_filename.png](./_resources/Euler_axis_angle_representation.resources/unknown_filename.png)
![unknown_filename.4.png](./_resources/Euler_axis_angle_representation.resources/unknown_filename.4.png)

The matrix is periodic (period 2\*pi)
![unknown_filename.1.png](./_resources/Euler_axis_angle_representation.resources/unknown_filename.1.png)

From rotation matrix
![unknown_filename.2.png](./_resources/Euler_axis_angle_representation.resources/unknown_filename.2.png)

If -1 < cos theta < 1: 
![unknown_filename.5.png](./_resources/Euler_axis_angle_representation.resources/unknown_filename.5.png)

If cos theta = 1: axis undefined

If cos theta = -1, e = any column of the following (apply normalisation to the column), whichever sign
![unknown_filename.3.png](./_resources/Euler_axis_angle_representation.resources/unknown_filename.3.png)

