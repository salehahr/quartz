---
title: Unit quaternions
date: "2021-05-14"
tags:
  - -sa/processed
  - math/quaternions
  - -published
---

**Parent**: [Quaternion index](math/rotations/quaternion-index.md), [orientation-parametrisations](orientation-parametrisations.md)  
**See also**: [quaternion-conventions](studienarbeit/quaternion-conventions.md), [quaternion double cover](math/rotations/quaternion-double-cover.md)

**Source**: [Solà 2017](solà-2017-quaternion-kinematics-for-eskf.md)

## Properties
$$
\begin{aligned}
\left\lVert \mathbf{q} \right\rVert &= 1\\
\mathbf{q}^{-1} &= \mathbf{q}^*
\end{aligned}
$$

Can be written in the form
$$
\mathbf{q} = \left[ \begin{array}{c}
	\cos\theta \\ \mathbf{u} \sin\theta
	\end{array} \right]
$$

![](/_img/quaternion_definition.png)

with
* $\mathbf{u}$ as a unit vector
* $\theta$ is the angle between $\mathbf{q}$ and the
	[identity quaternion](math/rotations/identity-quaternion.md)
	$\mathbf{q}_I = \left[\begin{array}{cccc}1 & 0 & 0 & 0\end{array}\right]^\text{T}$