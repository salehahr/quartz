---
title: (Phil's Lab) Sensor Fusion series
date: "2021-09-29"
mathjax: true
tags:
  - -sa/processing
  - -resources/videos
  - sensors/IMU
---

**Source**: https://www.youtube.com/watch?v=RZd6XDx5VXo

* [Sensor fusion](sensors/sensor-fusion.md)
* [Gyroscope](sensors/gyroscope.md)

## Example: UAV attitude estimation

![uav-angles](/_img/uav-angles.png)

**Goal**:
* To estimate roll and pitch angles of aircraft
* These angles are needed for feedback in autonomous control of an unmanned UAV

**We have**:
* 3-axis accelerometer [$\text{m/s}^2$]
* 3-axis gyroscope [$\text{rad/s}$]

**Note**:  
Here, angles are measured in *body* frame and not in fixed/inertial frame!

**Measured quantities**:
* acceleration  
	$\mathbf{a}_B = \left[\begin{array}{ccc}
			a_x & a_y & a_z \end{array}\right]^\text{T}$
* roll rates from gyrometer (body) $\neq$ derivative of [Euler angles](euler-angles) (fixed)  
	$\mathbf{\omega}_B = \left[\begin{array}{ccc}
			p & q & r \end{array}\right]^\text{T}
			\neq \left[\begin{array}{ccc}
			\dot{\phi} & \dot{\theta} & \dot{\psi} \end{array}\right]^\text{T}$


## Accelerometer
$$\mathbf{a} = \left[\begin{array}{ccc}
			a_x & a_y & a_z \end{array}\right]^\text{T}$$
			
### Accelerometer model
(Preliminary, doesn't account for everything yet -- the extra acceleration terms to be added would introduce a cross-correlation between the yaw $\psi$ and the other angles.)
$$\begin{aligned}
\left[\begin{array}{c}
			a_x  \\ a_y \\ a_z \end{array}\right]
	&= \frac{d\mathbf{v}}{dt}
		+ \mathbf{\omega}_B \times \mathbf{v}
		- \mathbf{R} \left( \begin{array}{c}
				0 \\ 0 \\ g
				\end{array} \right)
		+ \mathbf{\beta}(t)
		+ \mathbf{\eta}(t)
\end{aligned}$$

Variables	| Description
--- | ---
$\frac{d\mathbf{v}}{dt}$ | linear acceleration
$\mathbf{\omega}_B \times \mathbf{v}$ | acceleration due to translation + rotation
$\mathbf{g}$ | gravity vector
$\mathbf{\beta}$ | bias
$\mathbf{\eta}$ | noise (zero-mean, Gaussian)

If the accelerometer is at rest,
and ignoring noise/bias terms, the model is simplified to
$$\begin{aligned}
\left[\begin{array}{c}
			a_x  \\ a_y \\ a_z \end{array}\right]
	&= \left[ \begin{array}{c}
				g \sin \theta \\
				-g \cos\theta \sin\phi\\
				-g \cos\theta \cos\phi
				\end{array} \right]
\end{aligned}$$
and we can just rearrange the terms to get the roll $\phi$ and pitch $\theta$ angles.
$$
\begin{aligned}
\hat{\phi}_\text{acc} &= \tan^{-1}\left( \frac{a_y}{a_z} \right)\\
\hat{\theta}_\text{acc} &= \sin^{-1}\left( \frac{a_x}{g} \right)
\end{aligned}
$$

Drawbacks of the above angle estimation:
* Only true for accelerometer at rest
* Noise is present in real life (typically high frequency noise --> apply low-pass filter to measurements!)
* Time-varying bias term  
	--> how to estimate and cancel it out?  
	--> how to perform initial calibration?