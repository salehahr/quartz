---
title: Quaternion differentiation
date: "2021-05-14"
tags:
  - -sa/processed
  - math/quaternions
---

Parent: [Quaternion index](quaternion-index.md)
Source: J. D. Hol — Sensor fusion and calibration of inertial sensors, vision, ultra-wideband and GPS

![unknown_filename.3.png](./_resources/Quaternion_differentiation.resources/unknown_filename.3.png)

![unknown_filename.png](./_resources/Quaternion_differentiation.resources/unknown_filename.png)

![unknown_filename.2.png](./_resources/Quaternion_differentiation.resources/unknown_filename.2.png)

Using the identities:
![unknown_filename.1.png](./_resources/Quaternion_differentiation.resources/unknown_filename.1.png)

<http://math.stackexchange.com/questions/189185/quaternion-differentiation> 
Numerical differentiation (Euler)

<http://math.stackexchange.com/questions/1896379/how-to-use-the-quaternion-derivative>
q(t+dt) = q(t)\*dq

dq/dt = (1/2)\*W\*q
with  W = 0 + wx\*i + wy\*j + wz\*k.

Integrating
q(t) = q(t0)\*exp((1/2)\*W\*(t-t0))
\--> dq = exp((1/2)\*W\*dt).

