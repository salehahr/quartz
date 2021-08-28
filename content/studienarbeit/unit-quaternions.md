---
title: Unit quaternions
date: "2021-05-14"
tags:
  - -sa/processed
  - math/quaternions
---

**Parent**: [Quaternion index](quaternion-index.md), [orientation-parametrisations](orientation-parametrisations.md)
**Backlinks**: [Variables in ESKF](variables-in-eskf.md), [quaternion to rotation matrix](quaternion-to-rotation-matrix.md), [gibbs /-rodrigues-parameter](gibbs-_-rodrigues-parameter.md), [Which orientation parametrisation to choose](permanent/20.4-which-orientation-parametrisation-to-choose.md)

**Source**: [Solà 2017 Quaternion kinematics for ESKF](solà-2017-quaternion-kinematics-for-eskf.md)

## Properties

*   ![unknown_filename.png](./_resources/Unit_quaternions.resources/unknown_filename.png)
*   ![unknown_filename.1.png](./_resources/Unit_quaternions.resources/unknown_filename.1.png)

Can be written in the form
![unknown_filename.2.png](./_resources/Unit_quaternions.resources/unknown_filename.2.png)![unknown_filename.5.png](./_resources/Unit_quaternions.resources/unknown_filename.5.png)

with u as a unit vector
theta is the angle between q and the identity quaternion q\_I = \[1, 0, 0, 0\]

Double cover
Also:
![unknown_filename.3.png](./_resources/Unit_quaternions.resources/unknown_filename.3.png)![unknown_filename.6.png](./_resources/Unit_quaternions.resources/unknown_filename.6.png)
with phi as the angle rotated by q on objects in the 3D space

Therefore, the angle between a quaternion vector and the identity (in 4D) is half the angle rotated by the quaternion (in 3D)
![unknown_filename.4.png](./_resources/Unit_quaternions.resources/unknown_filename.4.png)

