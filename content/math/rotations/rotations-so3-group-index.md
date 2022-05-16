---
title: Rotations / SO(3) group index
date: "2021-08-16"
aliases:
  - /rotations/_index/
  - /rotations/index/
tags:
  - -master
  - -sa/processed
  - math/rotations
  - -resources/-bibliography
  - -resources/-bibliography/bib-to-read
  - -published
---

## Group theory
* [SE(3) Special Euclidian Group](math/rotations/se3-special-euclidian-group.md)
* [SO(3) 3D rotation group](math/rotations/so3-3d-rotation-group.md)
* [Lie group, Lie algebra](math/rotations/lie-group-lie-algebra.md)
	* [Exponential map](math/rotations/exponential-map.md)
	* [Logarithm map](math/rotations/logarithm-map.md)

## Ambiguities in rotation representations
* [Active/passive or Alibi/alias rotation transformations](math/rotations/active-passive-or-alibi-alias-transformations.md)
* [Intrinsic vs extrinsic rotations](math/rotations/intrinsic-vs-extrinsic-rotations.md)

Summary  

| &nbsp;  | Extrinsic/Global                                             | Intrinsic/Local                                              |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Active  | $\mathbf{x}_2 = T_2 T_1 \mathbf{x}_0$                        | $\mathbf{x}_2 = T_1 T_2 \mathbf{x}_0$                        |
| Passive | $\mathbf{x}^{\prime\prime} = T_1^{-1}\, T_2^{-1} \mathbf{x}$ | $\mathbf{x}^{\prime\prime} = T_2^{-1}\, T_1^{-1} \mathbf{x}$ |

* Active $\longleftrightarrow$ passive: invert transformation
* Global $\longleftrightarrow$ local: reverse transformation order

## Rotation representations  
[Orientation parametrisations](orientation-parametrisations)  
[Rotation error representation](math/rotations/rotation-error-representation.md)

* [Which orientation parametrisation to choose?](math/rotations/20.4-which-orientation-parametrisation.md)  
* [Linearisation of an orientation in SO(3)](studienarbeit/linearisation-of-an-orientation-in-so-3.md)

### As Euler angles
* [Euler angles](euler-angles.md)
* [Rotations as xyz Bryan-Tait angles (Kardanwinkel)](math/rotations/bryan-tait-kardanwinkel.md)

###  **Axis/angle**
*   [Euler axis/angle representation](math/rotations/euler-axis-angle-representation.md)

### **As quaternions**
*   [Quaternion index](math/rotations/quaternion-index.md)
*   [Quaternion to rotation matrix](math/rotations/quaternion-to-rotation-matrix.md)


## Kinematics
* [Kinematics primer](kinematics-primer.md)
* [Chaining rotation matrices and angular velocities](chaining-rotation-matrices-and-angular-velocities.md)

## IMU specific  
[IMU preintegration on manifold](imu-preintegration-on-manifold.md)

## To read
* [ ] https://rip94550.wordpress.com/2010/08/09/quaternions-and-rotations-1/