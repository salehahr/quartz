---
title: Euler angles
date: "2021-08-15"
external_url: "http://en.wikipedia.org/wiki/Davenport_chained_rotations"
tags:
  - -sa/processed
  - math/rotations
  - -published
---

**Parents**: [rotations-so3-group-index](math/rotations/rotations-so3-group-index.md), [orientation-parametrisations](orientation-parametrisations.md)  

**Source**: [Phil's Lab](bibliography/phils-lab-sensor-fusion.md)
* Three angles that describe the orientation of an object w.r.t. a *fixed* coordinate system
* Roll $\phi$, Pitch $\theta$, Yaw $\psi$

---

**Source**: [http://en.wikipedia.org/wiki/Euler\_angles](http://en.wikipedia.org/wiki/Euler_angles)

## Possible representations

*   Proper Euler angles (e.g. $zxz$) vs Tait-Bryan (e.g. $xyz$, $zyx$)
*   [Intrinsic vs. extrinsic rotations](math/rotations/intrinsic-vs-extrinsic-rotations.md)
	*   Extrinsic rotations (around fixed CS $xyz$)
	*   Intrinsic rotations (around body CS $XYZ = x''' y''' z'''$)

## As a rotation matrix
$$R = X(\alpha) Y(\beta) Z(\gamma)$$

This means either: (s. [Intrinsic vs extrinsic rotations](math/rotations/intrinsic-vs-extrinsic-rotations.md))

*   extrinsic rotations about z -> y -> x / yaw pitch roll
*   intrinsic rotations about x -> y' -> z'' = Z = z'''

**Note**:  Any extrinsic rotation is equivalent to an intrinsic rotation by the same angles but with inverted order of elemental rotations, and vice versa. \[[Source](http://en.wikipedia.org/wiki/Davenport_chained_rotations)\]

Intrinsic rotations $x-y’-z″$ by angles $\alpha, \beta, \gamma$ are equal to extrinsic rotations $z-y-x$ by angles $\gamma, \beta, \alpha$.

![unknown_filename.2.png](./_resources/Euler_angles.resources/unknown_filename.2.png)

Definition of X(alp), Y(beta), Z(gamma) \[elemental rotation matrix\] depends on convention chosen

Table of Euler rotation matrices (RH, active, intrinsic):

| Proper Euler | Tait-Bryan |
| --- | --- |
|     | ![unknown_filename.1.png](./_resources/euler_angles.resources/unknown_filename.1.png)<br>s. derivation here:  [bryan-tait-kardanwinkel](math/rotations/bryan-tait-kardanwinkel.md) |
|     | ![unknown_filename.png](./_resources/Euler_angles.resources/unknown_filename.png)<br>intrinsic yaw pitch roll |

---

**Source**: [Markley 2014](bibliography/markley-2014.md)

Table of Euler rotation matrices (RH, passive, intrinsic):
1: phi, 2:theta, 3:psi

| Proper Euler | Tait-Bryan |
| --- | --- |
|     | ![unknown_filename.3.png](./_resources/Euler_angles.resources/unknown_filename.3.png)<br>(transpose of the active version) |
|     | ![unknown_filename.4.png](./_resources/Euler_angles.resources/unknown_filename.4.png)<br>(transpose of the active version) |

Euler to quaternion conversions (note: these are all passive transformations??)
1: phi, 2:theta, 3:psi
![unknown_filename.5.png](./_resources/Euler_angles.resources/unknown_filename.5.png)

