---
title: Active/passive or Alibi/alias transformations
date: "2021-08-15"
tags:
  - -sa/processed
  - math/rotations
  - -published
---

**Parent**: [Rotations / SO(3) group index](math/rotations/rotations-so3-group-index.md)   
**See also**: [Intrinsic vs extrinsic rotations](math/rotations/intrinsic-vs-extrinsic-rotations.md)

**Sources**: [Wiki](http://en.wikipedia.org/wiki/Rotation_matrix%20-%20Ambiguities), [bonn-3D-cs](bibliography/bonn-3D-cs.md)

| Alibi / Active                                                                                                                                       | Alias / Passive                                                                                                |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| ![](/_img/active-trans.png)                                                                                                                          | ![](/_img/passive-trans.png)                                                                                   |
|                                                                                                                                                      | Point $\mathcal{x}$ doesn't change, but the coord vector representation changes to the 'prime' system          |
| ![](/_img/alibi-trafo.png)                                                                                                                           | ![](/_img/alias-trafo.png)                                                                                      |
| CS $S(x,\, y)$ is fixed                                                                                                                              | CS $S(x,\, y)$ is rotated                                                                                      |
| Point $\mathcal{x}$ rotates within fixed CS                                                                                                          | Point $\mathcal{x}$ remains stationary but is represented within a new CS                                      |
| $\mathcal{x}_1 \rightarrow \mathcal{x}_2$                                                                                                            | $S_1(x^\prime,y^\prime) \rightarrow  S_2(x^{\prime\prime}, y^{\prime\prime})$                                  |
| $\left( \begin{array}\cos\theta & -\sin\theta & 0\\ \sin\theta & \cos\theta & 0\\0 & 0 & 1\end{array} \right)$<br>Counterclockwise rotation by theta | $\left( \begin{array}\cos\theta & \sin\theta & 0\\ -\sin\theta & \cos\theta & 0\\0 & 0 & 1\end{array} \right)$ |
| ![5c2e55a0c26e29eecd9dd6e93ce2be77cd6611e0](http://wikimedia.org/api/rest_v1/media/math/render/svg/5c2e55a0c26e29eecd9dd6e93ce2be77cd6611e0)         |                                                                                                                |
| mathematics                                                                                                                                          | physics, robotics                                                                                              |

---

**Source**: [http://rock-learning.github.io/pytransform3d/transformation\_ambiguities.html](http://rock-learning.github.io/pytransform3d/transformation_ambiguities.html)
To transform between one another: use the inverse 

![](/_img/rotation-representations.png)


---

## Translations

**Source**: [bonn-3D-cs](bibliography/bonn-3D-cs.md)

### Active
| Equation                       |                             |
| ------------------------------ | --------------------------- |
| ![](/_img/active-trans-eq.png) | ![](/_img/active-trans.png) |


$$\mathbf{x}_2 = {}_2 \mathbf{T}^1\, \mathbf{x}_1$$

### Passive
| Equation                  |                              |
| ------------------------- | ---------------------------- |
| ![](/_img/passive-eq.png) | ![](/_img/passive-trans.png) |

$${}^2\mathbf{x} = {}^2 \mathbf{T}_1\, {}^1\mathbf{x}$$

## Relation between active and passive transformations
The passive transformation is the inverse of the active transformation!

**Active**
$$ \mathbf{x}_2 = \mathbf{T} \cdot \mathbf{x}_1 $$

**Passive**
$$ {}^2\mathbf{x} = \mathbf{T}^{-1} \cdot {}^1\mathbf{x} $$

**Extended notation**
$$
\begin{align}
{}_2 \mathbf{T}^1 &= \left( {}^2 \mathbf{T}_1 \right)^{-1}\\
{}_2 \mathbf{T}^1 &= {}^1 \mathbf{T}_2
\end{align}$$