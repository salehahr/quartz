---
title: Orientation parametrisations
date: "2021-03-23"
tags:
  - -sa/processed
  - discussion/2021/2021-04
  - math/rotations
  - math/quaternions
---

Parent: [Rotations / SO(3) group index](rotations _ so(3) group index.md), [quaternion index](quaternion index.md), [probabilistic models-for-imu](probabilistic-models-for-imu.md)
See also: [Rotation error representation](rotation-error-representation.md)

Source: [MKok 2017 Using inertial sensors for position and orientation estimation](mkok 2017 using inertial sensors-for-position-and-orientation-estimation.md)

Orientation parametrisations

*   Note: CCW rotation of a vector x\_v to x\_u corresponds to a CW rotation of the CS v to CS u.
*   Rotations in R^3 are a member of the [special orthogonal group SO(3)](special-orthogonal-group-so(3).md)

|     |     |
| --- | --- |
| rotation matrix | unique description of orientation |
| [Euler axis/angle](euler-axis_angle.md)<br>[rotation-vector](rotation-vector.md) | not unique, due to wrapping |
| [Euler angles](euler-angles.md) | not unique, due to wrapping and gimbal lock |
| [Unit quaternions](unit-quaternions.md) | not unique, -q and q depict the same orientation<br>Proof: <http://math.stackexchange.com/questions/2016282/negative-quaternion> |
| [Gibbs / Rodrigues parameter](gibbs-_-rodrigues-parameter.md) | infinite for 180 degree rotations, but 1:1 mapping between itself and unit quaternions |

Next: [Which orientation parametrisation to choose?](permanent/20.4-which-orientation-parametrisation-to-choose.md)

