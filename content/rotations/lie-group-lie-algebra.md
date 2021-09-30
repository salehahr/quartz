---
title: Lie group, Lie algebra
date: "2021-07-23"
tags:
  - -sa/processed
  - math/rotations
  - -published
  - -definitions
---

# Lie group

**Parent**: [Rotations / SO(3) group index](rotations-so3-group-index.md)  
**Source**: <http://www.seas.upenn.edu/~meam620/slides/kinematicsI.pdf>

A group that is a differentiable (smooth) [manifold](manifolds.md) is called a Lie group.


# Lie algebra

**Source**: [http://en.wikipedia.org/wiki/3D\_rotation\_group](http://en.wikipedia.org/wiki/3D_rotation_group)

Lie algebra $\mathfrak{so}(3)$

*   Every Lie group has an associated Lie algebra
*   Lie algebra: linear space with same dimension as the Lie group
*   Consists of all skew-symmetric 3x3 matrices
*   Elements of the Lie algebra $\mathfrak{so}(3)$ are elements of the tangent space of the manifold SO(3)/Lie group at the [identity element](rotations/identity-of-a-group.md).

---

**Source**: [Forster 2017 IMU Preintegration](forster-2017-imu-preintegration.md)

An Euler vector $\mathbf{\omega} = \left(x,y,z\right) \in \mathbb{R}^3$ can be represented by a skew symmetric matrix in the Lie algebra

$$
\hat{\mathbf{\omega}} = \left[\begin{array}{ccc}
	0 & -z & y\\
	z & 0 & -x\\
	-y & x & 0
	\end{array}\right] \in \mathfrak{so}(3)
$$

![lie-group-maps](_img/lie-group-maps.png)

**Mappings**:
* [Exponential map](rotations/exponential-map.md)
* [Logarithm map](rotations/logarithm-map.md)

