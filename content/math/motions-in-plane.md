---
title: motions-in-plane
date: 2022-05-14
tags:
  - math
  - math/rotations
---

# Motions in the plane

**Source**: [bonn-3D-cs](bibliography/bonn-3D-cs.md)

Rotation of $\mathcal{X}$ to $\mathcal{X}^\prime$  
$$ 
\begin{align}
\left[
\begin{array} ~x \\ y \end{array}
\right]
&= 
\left[
\begin{array} ~r\cos \alpha \\ y\cos \alpha \end{array}
\right]\\

\mathcal{X}^\prime = \mathcal{R}(\mathcal{X}) : ~
\left[
\begin{array} ~x^\prime \\ y^\prime \end{array}
\right]
&= 
\left[
\begin{array}
~\cos\gamma & -\sin\gamma \\
\sin\gamma & \cos\gamma \end{array}
\right]
\left[
\begin{array} ~x \\ y \end{array}
\right]
\end{align}
$$
![](/_img/basic-plane-rotation.png)

## Basic homogeneous transformations
### Translation of $\mathbf{t}$
$$
\begin{align}
\mathbf{x}^\prime &= \mathbf{T} \mathbf{x} \\
\text{with } \mathbf{T} &=
\left[
\begin{array}
\mathbf{I} & \mathbf{t}\\
\mathbf{0}^\text{T} & 1
\end{array}
\right]
\end{align}
$$

### Rotation around origin by $\varphi$
$$
\begin{align}
\mathbf{x}^\prime &= \mathbf{T} \mathbf{x} \\
\text{with } \mathbf{T} &=
\left[
\begin{array}
\mathbf{R} & \mathbf{0}\\
\mathbf{0}^\text{T} & 1
\end{array}
\right]
=
\left[
\begin{array}
\cos\varphi & -\sin\varphi & 0\\
\sin\varphi & \cos\varphi & 0\\
0 & 0 & 1
\end{array}
\right]
\end{align}
$$

## Inverse homogeneous transformations
### Translation
$$
\mathbf{T}^{-1}
=
\left[
\begin{array}
\mathbf{I} & -\mathbf{t}\\
\mathbf{0}^\text{T} & 1
\end{array}
\right]
$$

### Rotation
$$
\mathbf{T}^{-1}
=
\left[
\begin{array}
\mathbf{R}^{-1} & \mathbf{0}\\
\mathbf{0}^\text{T} & 1
\end{array}
\right]
=
\left[
\begin{array}
\mathbf{R}^{\text{T}} & \mathbf{0}\\
\mathbf{0}^\text{T} & 1
\end{array}
\right]
$$
