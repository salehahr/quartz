---
title: Gibbs / Rodrigues parameter representation for rotations
date: "2021-08-17"
tags:
  - to-do/to-clarify
  - -sa/processed
  - math/rotations
  - math/quaternions
  - -published
---

**Parent**: [Orientation parametrisations](orientation-parametrisations.md)   
**See also**: [Rotation error representation](rotations/rotation-error-representation.md)

**Source**: [Markley 2014](markley-2014.md)

From [unit quaternions](rotations/unit-quaternions.md):
![Image.png](studienarbeit/_resources/Gibbs___Rodrigues_parameter_representation_for_rotations.resources/Image.png)

From [euler-axis-angle-representation](rotations/euler-axis-angle-representation.md):
![unknown_filename.2.png](studienarbeit/_resources/Gibbs___Rodrigues_parameter_representation_for_rotations.resources/unknown_filename.2.png)

To [unit quaternions](rotations/unit-quaternions.md): 

 ![unknown_filename.1.png](studienarbeit/_resources/Gibbs___Rodrigues_parameter_representation_for_rotations.resources/unknown_filename.1.png)

![unknown_filename.png](studienarbeit/_resources/Gibbs___Rodrigues_parameter_representation_for_rotations.resources/unknown_filename.png)

*   Plane of the figure contains identity quaternion, origin
*   The circle is a cross section of the quaternion sphere S^3
*   The upper horizontal axis is the 3D Gibbs vector hyperplane (tangent at the identity quaternion)

\[+\] q and -q map to the same Gibbs vector, therefore there is a 1:1 mapping of rotations between quaternions and the Gibbs parameter
\[-\] the Gibbs vector is infinite for 180 degree rotations (q.w = q4 = 0? - [ ] )

*   therefore not good for global orientation representations,
*   but good for representation of small rotations

