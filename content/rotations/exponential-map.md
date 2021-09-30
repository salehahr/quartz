---
title: Exponential map
date: "2021-07-23"
tags:
  - -definitions
  - -sa/processed
  - math/rotations
  - math/quaternions
  - -published
---

**Parents**: [Quaternion index](rotations/quaternion-index.md), [Rotations / SO(3) group index](rotations-so3-group-index.md)

## Notation

### Variables
$$\begin{alignedat}{3}
&\phi &&\in \mathbb{R}^3\\
&\phi^\wedge &&\in \mathfrak{so}(3)\\
&\mathbf{R} &&\in \text{SO}(3)\\
\end{alignedat}$$

### Functions
$$\begin{alignedat}{3}
\text{(skew) } \wedge &:& \mathbb{R}^3 &&\rightarrow \mathfrak{so}(3) &\\
\exp		&:& ~&&\mathfrak{so}(3) &\rightarrow \text{SO}(3)\\
\text{Exp}	&:& ~\mathbb{R}^3	 
		&&
		&\rightarrow \text{SO}(3)
\end{alignedat}$$

<pre></pre>
Thus,
$$\begin{alignedat}{3}
&\exp(\phi^\wedge) = \text{Exp}(\phi) = \mathbf{R}
\end{alignedat}$$

----

**Source**: [Forster 2017 IMU Preintegration](forster-2017-imu-preintegration.md)

## At the identity 
Maps an element of the [Lie algebra](lie-group-lie-algebra.md)
($\phi^\wedge \in \mathfrak{so}(3)$, a skew symmetric matrix)
to a rotation
![unknown_filename.1.png](studienarbeit/_resources/Exponential_map.resources/unknown_filename.1.png)

First order approximation
$$ \exp(\phi^\wedge) \approx \mathbf{I} + \phi^\wedge$$


## Some properties of the exponential map
*   Perturbations, first order approximation
    ![unknown_filename.3.png](studienarbeit/_resources/Exponential_map.resources/unknown_filename.3.png)
    with the right Jacobian of SO(3)
    ![unknown_filename.4.png](studienarbeit/_resources/Exponential_map.resources/unknown_filename.4.png)
    
*   $J_r(\phi) = \mathbf{I}$ for very small angles
*   Following the Adjoint expression
    ![unknown_filename.5.png](studienarbeit/_resources/Exponential_map.resources/unknown_filename.5.png)
    

- [x] difference between Exp and exp? — I think exp acts on the skew-sym matrix; Exp acts on the corresp. rotation vector

* * *

**Source**: [MKok 2017](mkok-2017.md)

## Approximations for small perturbations
$$
\begin{aligned}
\exp_q(\eta) &\approx \left( \begin{array}{c}1 \\ \eta\end{array} \right)\\
\exp_R(\eta) &\approx \mathbf{I}_3 + \left[ \eta \times\right]
\end{aligned}
$$

**Note**: in this source, $\exp_q$ and $\exp_R$ equivalent to the $\text{Exp}$ notation in other sources.
So here, $\eta$ is implicitly converted either to $\left[ \eta \times\right]$ or $\eta/2$ in an intermediate step.
