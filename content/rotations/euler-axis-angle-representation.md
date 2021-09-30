---
title: Euler axis/angle representation
date: "2021-08-17"
tags:
  - -sa/processed
  - math/rotations
  - -published
---

**Parents**: [rotations-so3-group-index](rotations/rotations-so3-group-index.md), [orientation-parametrisations](orientation-parametrisations.md)    
**See also**: [Rotation vector representation](rotation-vector-representation.md)  

**Source**: [Markley 2014](bibliography/markley-2014.md)

3 parameters:

*  there appears to be 4 parameters: 1 angle, 3-component unit vector (Euler axis, Euler angle of the rotation)
*   however, the vector $\mathbf{e}$ is a unit vector (constrained by $\left\lVert \mathbf{e} \right\rVert = 1$

### To rotation matrix
![unknown_filename.png](studienarbeit/_resources/Euler_axis_angle_representation.resources/unknown_filename.png)
![unknown_filename.4.png](studienarbeit/_resources/Euler_axis_angle_representation.resources/unknown_filename.4.png)

The matrix is periodic (period 2\*pi)
![unknown_filename.1.png](studienarbeit/_resources/Euler_axis_angle_representation.resources/unknown_filename.1.png)

### From rotation matrix
![unknown_filename.2.png](studienarbeit/_resources/Euler_axis_angle_representation.resources/unknown_filename.2.png)

If -1 < cos theta < 1: 
![unknown_filename.5.png](studienarbeit/_resources/Euler_axis_angle_representation.resources/unknown_filename.5.png)

If cos theta = 1: axis undefined

If cos theta = -1, e = any column of the following (apply normalisation to the column), whichever sign
![unknown_filename.3.png](studienarbeit/_resources/Euler_axis_angle_representation.resources/unknown_filename.3.png)

