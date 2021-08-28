---
title: Euler angles
date: "2021-08-15"
external_url: "http://en.wikipedia.org/wiki/Davenport_chained_rotations"
tags:
  - -sa/processed
  - math/rotations
---

Parents: [Rotations / SO(3) group index](rotations _ so(3)-group-index.md), [orientation-parametrisations](orientation-parametrisations.md)
Backlinks: [Orientation parametrisations](orientation-parametrisations.md)

Source: [http://en.wikipedia.org/wiki/Euler\_angles](http://en.wikipedia.org/wiki/Euler_angles)

Possible representations

*   Proper Euler angles (e.g. zxz) vs Tait-Bryan (e.g. xyz, zyx)
*   Extrinsic rotations (around fixed CS xyz) vs intrinsic rotations (around body CS XYZ = x''' y''' z''')

As a rotation matrix
![ab48abbc214df3633ab0262c3ef043bbd497a38d](http://wikimedia.org/api/rest_v1/media/math/render/svg/ab48abbc214df3633ab0262c3ef043bbd497a38d)

This means either: (s. [Intrinsic vs extrinsic rotations](intrinsic-vs-extrinsic-rotations.md))

*   extrinsic rotations about z -> y -> x / yaw pitch roll
*   intrinsic rotations about x -> y' -> z'' = Z = z'''

Note:  Any extrinsic rotation is equivalent to an intrinsic rotation by the same angles but with inverted order of elemental rotations, and vice versa. \[[Source](http://en.wikipedia.org/wiki/Davenport_chained_rotations)\]
intrinsic rotations x-y’-z″ by angles α, β, γ == extrinsic rotations z-y-x by angles γ, β, α

![unknown_filename.2.png](./_resources/Euler_angles.resources/unknown_filename.2.png)

Definition of X(alp), Y(beta), Z(gamma) \[elemental rotation matrix\] depends on convention chosen

Table of Euler rotation matrices (RH, active, intrinsic):

|     |     |
| --- | --- |
| Proper Euler | Tait-Bryan |
|     | ![unknown_filename.1.png](./_resources/euler_angles.resources/unknown_filename.1.png)<br>s. derivation here:  [rotations as xyz bryan-tait angles (kardanwinkel)](rotations-as-xyz-bryan-tait-angles-(kardanwinkel).md) |
|     | ![unknown_filename.png](./_resources/Euler_angles.resources/unknown_filename.png)<br>intrinsic yaw pitch roll |

Source: [Markley Fundamentals of Spacecraft Attitude Determination](markley-fundamentals-of-spacecraft-attitude-determination.md)

Table of Euler rotation matrices (RH, passive, intrinsic):
1: phi, 2:theta, 3:psi

|     |     |
| --- | --- |
| Proper Euler | Tait-Bryan |
|     | ![unknown_filename.3.png](./_resources/Euler_angles.resources/unknown_filename.3.png)<br>(transpose of the active version) |
|     | ![unknown_filename.4.png](./_resources/Euler_angles.resources/unknown_filename.4.png)<br>(transpose of the active version) |

Euler to quaternion conversions (note: these are all passive transformations??)
1: phi, 2:theta, 3:psi
![unknown_filename.5.png](./_resources/Euler_angles.resources/unknown_filename.5.png)

