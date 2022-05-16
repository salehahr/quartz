---
title: Quaternion double cover
date: "2021-09-30"
tags:
  - -sa/processed
  - math/quaternions
  - -published
---

**Parent**: [Quaternion index](math/rotations/quaternion-index.md)

**Source**: [Solà 2017](solà-2017-quaternion-kinematics-for-eskf.md)

$$
\mathbf{q}
	= \left[ \begin{array}{c}
		q_w\\ \mathbf{q}_v
		\end{array} \right]
	= \left[ \begin{array}{c}
		\cos\frac{\phi}{2} \\ \mathbf{u} \sin\frac{\phi}{2}
		\end{array} \right]
$$
where $\phi$ is the angle rotated by $\mathbf{q}$ on objects in the 3D space $\mathbb{R}^3$.

![quaternion-double-cover](/_img/quaternion-double-cover.png)

### Recap
* $\theta$ is the angle in quaternion space (s. [unit quaternions](math/rotations/unit-quaternions.md))
* $\phi$ as the angle in 3D space $\mathbb{R}^3$

Therefore, the angle is halved in quaternion space.
$$\theta = \phi / 2$$
