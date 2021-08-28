---
title: SO(3) 3D rotation group
date: "2020-11-27"
tags:
  - -definitions
  - -sa/processed
  - math/rotations
---

Parent: [Rotations / SO(3) group index](rotations-_-so(3)-group-index.md)
See also: [Orientation parametrisations](orientation parametrisations.md), [linearisation of an orientation in so(3)](linearisation of an orientation in so(3).md), [solà 2017 quaternion kinematics for eskf](solà-2017-quaternion-kinematics-for-eskf.md)

Source: [MKok 2017 Using inertial sensors for position and orientation estimation](mkok 2017 using inertial sensors-for-position-and-orientation-estimation.md)

*   All orthogonal matrices with dim 3x3 have the property ![unknown_filename.6.png](./_resources/SO(3)_3D_rotation_group.resources/unknown_filename.6.png)
*   They are part of the orthogonal group O(3)
*   If, additionally, det R = 1, then the matrix belongs to SO(3) and is a rotation matrix

* * *

Source: [http://en.wikipedia.org/wiki/3D\_rotation\_group](http://en.wikipedia.org/wiki/3D_rotation_group)

The SO(3) group

*   Group of all rotations about the origin of the 3D space (Euclidian space, R^3)
*   Has a natural structure as a smooth [manifold](manifold.md)
    *   Group operations on the manifold are smoothly differentiable
    *   Is therefore a [Lie group](lie-group.md)
*   Compact, dim = 3

Rotations in general

*   Rotations are linear transformations of R^3
*   Can be represented as matrices using an orthonormal basis of R^3
*   These matrices are called 'special orthogonal matrices', i.e. SO(3)

* * *

Source: [Forster 2017 IMU Preintegration](forster-2017-imu-preintegration.md)

![Image.png](./_resources/SO(3)_3D_rotation_group.resources/Image.png)

Mappings
[Exponential map](exponential-map.md), [logarithm-map](logarithm-map.md)

Uncertainty description in SO(3)

*   Define a distribution in the tangent space (Lie algebra)
*   Map the distribution in the tangent space to SO(3) via the exponential map
*   We get the random variable ![unknown_filename.2.png](./_resources/SO(3)_3D_rotation_group.resources/unknown_filename.2.png)

![unknown_filename.png](./_resources/SO(3)_3D_rotation_group.resources/unknown_filename.png)    ![unknown_filename.1.png](./_resources/SO(3)_3D_rotation_group.resources/unknown_filename.1.png)

Distribution of the random variable:
![unknown_filename.4.png](./_resources/SO(3)_3D_rotation_group.resources/unknown_filename.4.png)

When Sigma is small, the normalisation factor can be approximated to
![unknown_filename.3.png](./_resources/SO(3)_3D_rotation_group.resources/unknown_filename.3.png)

If the normalisation factor beta is approximated as a constant, the negative log-likelihood of a rotation R given its measurement is
![unknown_filename.5.png](./_resources/SO(3)_3D_rotation_group.resources/unknown_filename.5.png)

