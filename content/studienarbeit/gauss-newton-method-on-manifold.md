---
title: Gauss-Newton Method on Manifold
date: "2020-11-27"
tags:
  - -sa/processed
  - sensors/IMU/preintegration
  - math
---

Source: [Forster 2017 IMU Preintegration](forster-2017-imu-preintegration.md)

Standard approach for optimization on manifold

*   define a retraction to reparametrise the problem (lifting)
*   retraction ![unknown_filename.4.png](./_resources/Gauss-Newton_Method_on_Manifold.resources/unknown_filename.4.png)
    *   bijective map
    *   map between an element of the tangent space at x and a neighbourhood of x on the manifold
*   i.e. we work in the tangent space (locally like a Euclidian space) and apply standard optimisation techniques
*   for Gauss-Newton specifically:
    *   \[ts\] squared cost around current estimate
    *   \[ts\] solve the quadratic approximation --> we get vector ![unknown_filename.2.png](./_resources/Gauss-Newton_Method_on_Manifold.resources/unknown_filename.2.png) in tangent space
    *   \[m\] update the current guess on the manifold ![unknown_filename.3.png](./_resources/Gauss-Newton_Method_on_Manifold.resources/unknown_filename.3.png) 

Consider: ![unknown_filename.png](./_resources/Gauss-Newton_Method_on_Manifold.resources/unknown_filename.png)
Reparametrised: ![unknown_filename.1.png](./_resources/Gauss-Newton_Method_on_Manifold.resources/unknown_filename.1.png)

Retraction for SE(3)
The exponential map of SE(3) as a retraction is possible, but may not be convenient (computationally)

The following retraction is proposed (at ![unknown_filename.5.png](./_resources/Gauss-Newton_Method_on_Manifold.resources/unknown_filename.5.png)):
![unknown_filename.6.png](./_resources/Gauss-Newton_Method_on_Manifold.resources/unknown_filename.6.png)        ![unknown_filename.7.png](./_resources/Gauss-Newton_Method_on_Manifold.resources/unknown_filename.7.png)

Using this rectraction, we don't need to compute the exponential map for SE(3)

