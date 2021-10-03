---
title: Gyroscope/Gyrometer
date: "2021-09-29"
mathjax: true
tags:
  - -sa/processing
  - sensors
---

**Source**: [Phil's Lab](bibliography/phils-lab-sensor-fusion.md)

## Gyroscope model
$$
\begin{aligned}
\mathbf{\omega}_B &=
	\mathbf{\omega}_\text{true}
	+ \mathbf{\beta}(t)
	+ \mathbf{\eta}(t)
\end{aligned}
$$

We need to transform these *body* rates to [Euler](euler-angles) rates!
$$
\begin{aligned}
\left[ \begin{array}{c} \dot{\phi} \\ \dot{\theta} \end{array} \right]
&= \left[ \begin{array}{ccc}
	1 & \sin\phi \tan\theta & \cos\phi\tan\theta\\
	0 & \cos\phi & -\sin\phi
	\end{array} \right]
	\left[ \begin{array}{c}p\\q\\r\end{array} \right]
\end{aligned}
$$


Problem: $\phi$ and $\theta$ need to be known!  
--> integrate?
$$\hat{\phi} = \int_0^T \dot{\phi}(t) ~dt ~?$$

Direct integration not possible due to the presence of time-varying bias and noise; integration leads to gyroscope drift (we integrate the noise/error terms so we drift away from the true value)!
$$\hat{\phi} = \int_0^T  \dot{\phi}(t) + \beta_\phi(t) + \eta_\phi(t) ~dt$$

## Conclusions
* Using only the gyroscope provides a good estimate over short periods of time (due to integration of bias terms)
* If using for a short period of time, the drift won't affect us too much (not had time to accumulate)