---
title: Exponential map
date: "2021-07-23"
tags:
  - -definitions
  - -sa/processed
  - math/rotations
  - math/quaternions
---

Parent: [Quaternion index](quaternion index.md), [rotations / so(3) group-index](rotations-_-so(3)-group-index.md)
Backlinks: [Linearisation of an orientation in SO(3)](linearisation-of-an-orientation-in-so(3).md)

Source: [Forster 2017 IMU Preintegration](forster-2017-imu-preintegration.md)

![unknown_filename.png](./_resources/Exponential_map.resources/unknown_filename.png)
\[At the identity\] maps an element of the [lie-algebra](lie-algebra.md) (a skew symmetric matrix) to a rotation
![unknown_filename.1.png](./_resources/Exponential_map.resources/unknown_filename.1.png)

First order approximation
![unknown_filename.2.png](./_resources/Exponential_map.resources/unknown_filename.2.png)

Some properties of the exponential map

*   Perturbations, first order approximation
    ![unknown_filename.3.png](./_resources/Exponential_map.resources/unknown_filename.3.png)
    with the right Jacobian of SO(3)
    ![unknown_filename.4.png](./_resources/Exponential_map.resources/unknown_filename.4.png)
    
*   Jr = I for  (very small angles)
*   Following the Adjoint expression
    ![unknown_filename.5.png](./_resources/Exponential_map.resources/unknown_filename.5.png)
    

- [x] difference between Exp and exp? — I think exp acts on the skew-sym matrix; Exp acts on the corresp. rotation vector

* * *

Source: [MKok 2017 Using inertial sensors for position and orientation estimation](mkok 2017 using inertial sensors-for-position-and-orientation-estimation.md)

Approximations for small perturbations
![unknown_filename.6.png](./_resources/Exponential_map.resources/unknown_filename.6.png)

