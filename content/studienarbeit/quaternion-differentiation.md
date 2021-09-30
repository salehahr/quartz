---
title: Quaternion differentiation
date: "2021-05-14"
tags:
  - -sa/processed
  - math/quaternions
---

**Parent**: [Quaternion index](rotations/quaternion-index.md)  
**Source**: J. D. Hol — Sensor fusion and calibration of inertial sensors, vision, ultra-wideband and GPS

![unknown_filename.3.png](./_resources/Quaternion_differentiation.resources/unknown_filename.3.png)

![unknown_filename.png](./_resources/Quaternion_differentiation.resources/unknown_filename.png)

![unknown_filename.2.png](./_resources/Quaternion_differentiation.resources/unknown_filename.2.png)

Using the identities:
![unknown_filename.1.png](./_resources/Quaternion_differentiation.resources/unknown_filename.1.png)

---

<http://math.stackexchange.com/questions/189185/quaternion-differentiation>    
Numerical differentiation (Euler)

---

<http://math.stackexchange.com/questions/1896379/how-to-use-the-quaternion-derivative>

$$
\begin{aligned}
q(t+dt) &= q(t) \otimes dq\\
\dfrac{dq}{dt} &= \frac{1}{2} \omega \otimes q
	\quad \text{with }
	\omega = \left[ 
		\begin{array}{cccc}
			0 & \omega_x & \omega_y & \omega_z
		\end{array}
		\right]^\text{T}
\end{aligned}$$

Integrating this, assuming $\omega=\text{const.}$ from $t_0$ to $t_0 + dt$:
$$
\begin{aligned}
q(t) &= q(t_0) \exp \left( \frac{1}{2} \omega \cdot \left( t - t_0\right) \right)\\
\rightarrow dq &= \exp \left( \frac{1}{2} \omega \cdot dt \right)
\end{aligned}
$$

