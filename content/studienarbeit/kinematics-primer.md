---
title: Kinematics primer
date: "2021-05-24"
tags:
  - -master
  - -sa/processed
  - math/kinematics
  - discussion/2021/2021-06
---

Source: [Hibbeler Dynamics](hibbeler-dynamics.md), [woernle-mehrkörpersysteme](woernle-mehrkörpersysteme.md)
See also: [Reversed kinematics relations](reversed-kinematics-relations.md), [denavit-hartenberg-convention](denavit-hartenberg-convention.md)
Backlinks: [Obtaining IMU measurements from camera by forward kinematics](obtaining imu measurements from camera by forward kinematics.md), [rotations / so(3) group-index](rotations-_-so(3)-group-index.md)

Prereqs:

*   [Chaining rotation matrices and angular velocities](chaining-rotation-matrices-and-angular-velocities.md)
*   [Converting velocity from CS1 to CS0](converting-velocity-from-cs1-to-cs0.md)
*   [Poisson equation for skew symmetric matrix of angular velocity](poisson equation for skew-symmetric-matrix-of-angular-velocity.md)
*   [Inverse of a homogeneous transformation matrix](inverse-of-a-homogeneous-transformation-matrix.md)
*   [Differentiation in different coordinate systems](differentiation-in-different-coordinate-systems.md)

|     |     |
| --- | --- |
| Position (in world coordinates)<br>![unknown_filename.png](./_resources/kinematics_primer.resources/unknown_filename.png)<br><br>![unknown_filename.5.png](./_resources/kinematics_primer.resources/unknown_filename.5.png)<br><br>velocity (in world coordinates)<br>![unknown_filename.1.png](./_resources/kinematics_primer.resources/unknown_filename.1.png)<br>![unknown_filename.2.png](./_resources/kinematics_primer.resources/unknown_filename.2.png)<br><br>![unknown_filename.7.png](./_resources/kinematics_primer.resources/unknown_filename.7.png)<br>where the skew symmetric matrix is the angular velocity of cs1 relative to cs0,<br>(~~given in cs1 coordinates? ~~ cs whatever - [x] )<br><br>acceleration (in world coordinates)<br>![unknown_filename.3.png](./_resources/kinematics_primer.resources/unknown_filename.3.png)<br>![unknown_filename.4.png](./_resources/kinematics_primer.resources/unknown_filename.4.png)<br><br>![unknown_filename.9.png](./_resources/kinematics_primer.resources/unknown_filename.9.png) |-![unknown_filename.8.png](./_resources/kinematics_primer.resources/unknown_filename.8.png)<br>[hibbeler-dynamics](hibbeler-dynamics.md)<br><br>![unknown_filename.6.png](./_resources/kinematics_primer.resources/unknown_filename.6.png)<br>[woernle-mehrkörpersysteme](woernle-mehrkörpersysteme.md) |

