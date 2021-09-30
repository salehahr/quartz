---
title: SE(3) Special Euclidian Group
date: "2020-11-27"
tags:
  - -definitions
  - -sa/processed
  - math/rotations
  - -published
---

**Source**: [Forster 2017 -- IMU Preintegration](forster-2017-imu-preintegration.md)

Group of rigid motion in 3D.  
Consists of 
* a rotation in [SO(3)](rotations/so3-3d-rotation-group.md)
* a translation in $\mathbb{R}^3$

$$\begin{aligned}
\text{SE}(3) \dot{=} \left\lbrace
		\left(\mathbf{R}, \mathbf{p}
			\right) :
			\mathbf{R} \in \text{SO}(3),
			\mathbf{p} \in \mathbb{R}^3
	\right\rbrace
\end{aligned}$$

$$\begin{aligned}
\mathbf{T}_1\mathbf{T}_2 &= \left(
	\mathbf{R}_1\mathbf{R}_2,
	\mathbf{R}_1\mathbf{p}_2 + \mathbf{p}_1
	\right)\\
\mathbf{T}_1^{-1} &= \left(
	\mathbf{R}_1^\text{T}, -\mathbf{R}_1^{\text{T}}\mathbf{p}_1
	\right)
\end{aligned}$$


