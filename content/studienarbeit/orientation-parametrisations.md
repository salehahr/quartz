---
title: Orientation parametrisations
date: "2021-03-23"
tags:
  - -sa/processed
  - discussion/2021/2021-04
  - math/rotations
  - math/quaternions
  - -published
---

**Parents**: [rotations-so3-group-index](rotations/rotations-so3-group-index.md), [quaternion index](rotations/quaternion-index.md), [probabilistic models-for-imu](probabilistic-models-for-imu.md)  
**See also**: [Rotation error representation](rotations/rotation-error-representation.md)

**Source**: [MKok 2017](mkok-2017.md), [markley-2014](bibliography/markley-2014.md)

Orientation parametrisations

*   Note: CCW rotation of a vector $x_v$ to $x_u$ corresponds to a CW rotation of the CS $v$ to CS $u$ (see also [active/passive transformations](rotations/active-passive-or-alibi-alias-rotation-transformations.md)).
*   Rotations are a member of [SO(3)](rotations/so3-3d-rotation-group.md)

| rotation matrix | unique description of orientation |
| --- | --- |
| [Euler axis/angle](rotations/euler-axis-angle-representation.md)<br>[Rotation vector](studienarbeit/rotation-vector-representation.md) | not unique, due to wrapping |
| [Euler angles](euler-angles.md) | not unique, due to wrapping and gimbal lock |
| [Unit quaternions](rotations/unit-quaternions.md) | not unique, -q and q depict the same orientation<br>Proof: <http://math.stackexchange.com/questions/2016282/negative-quaternion> |
| [Gibbs / Rodrigues parameter](rotations/gibbs-rodrigues-parameter.md) | infinite for 180 degree rotations, but 1:1 mapping between itself and unit quaternions |

Next: [Which orientation parametrisation to choose?](rotations/20.4-which-orientation-parametrisation.md)

