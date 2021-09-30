---
title: SO(3) 3D rotation group
date: "2020-11-27"
tags:
  - -definitions
  - -sa/processed
  - math/rotations
  - -published
---

**Parent**: [Rotations / SO(3) group index](rotations-so3-group-index.md)  
**See also**: [Orientation parametrisations](orientation-parametrisations.md), [Linearisation of an orientation](studienarbeit/linearisation-of-an-orientation-in-so-3.md), [Solà 2017 quaternion kinematics for eskf](solà-2017-quaternion-kinematics-for-eskf.md)

**Source**: [MKok 2017](studienarbeit/mkok-2017.md)

*   All orthogonal matrices with dim 3x3 have the property  
		$$RR^\text{T} = R^\text{T}R = I_3$$
*   They are part of the orthogonal group O(3)
*   If, additionally, $\det R = 1$, then the matrix belongs to SO(3) and is a rotation matrix

* * *

**Source**: [http://en.wikipedia.org/wiki/3D\_rotation\_group](http://en.wikipedia.org/wiki/3D_rotation_group)

The SO(3) group

*   Group of all rotations about the origin of the 3D space (Euclidian space, $\mathbb{R}^3$)
*   Has a natural structure as a smooth [manifold](studienarbeit/manifolds.md).
    *   Group operations on the manifold are smoothly differentiable
    *   Is therefore a [Lie group](rotations/lie-group-lie-algebra.md)
*   Compact, dim = 3

Rotations in general

*   Rotations are linear transformations of $\mathbb{R}^3$
*   Can be represented as matrices using an orthonormal basis of $\mathbb{R}^3$
*   These matrices are called 'special orthogonal matrices', i.e. SO(3)

* * *

**Source**: [Forster 2017 IMU Preintegration](forster-2017-imu-preintegration.md)  
**See**: [Lie group](rotations/lie-group-lie-algebra.md)

Uncertainty description in SO(3)

*   Define a distribution in the tangent space (Lie algebra)
*   Map the distribution in the tangent space to SO(3) via the exponential map
*   We get the random variable $\tilde{R} \in \text{SO}(3)$
		$$\begin{aligned}
		\tilde{R} &= \mathbf{R}~ \text{Exp}(\varepsilon)
			\quad \varepsilon \sim \mathcal{N} (0, \Sigma)
		\end{aligned}$$

Distribution $p(\tilde{R})$ of the random variable:
![unknown_filename.4.png](studienarbeit/_resources/SO(3)_3D_rotation_group.resources/unknown_filename.4.png)

When $\Sigma$ is small, the normalisation factor can be approximated to
![unknown_filename.3.png](studienarbeit/_resources/SO(3)_3D_rotation_group.resources/unknown_filename.3.png)

If the normalisation factor beta is approximated as a constant, the negative log-likelihood of a rotation R given its measurement is
![unknown_filename.5.png](studienarbeit/_resources/SO(3)_3D_rotation_group.resources/unknown_filename.5.png)

