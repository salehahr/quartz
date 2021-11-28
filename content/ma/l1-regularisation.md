---
title: l1-regularisation
date: 2021-11-28
tags:
  - machine-learning
---

**Parent**: [regularisation](ma/regularisation.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)


# L$_1$ regularisation
* Relaxed version of an [L$_0$ regularisation](ma/l0-regularisation.md)
* Penalises the sum of the absolute values of the weights
* Regularisation term:
	$$\left\lvert \mathbf{w} \right\rvert = 
	\left| |w_1| + \dots + |w_n| \right|$$
* Convex problem
* Encourages a **sparse model**: model will want to drive $w$ to zero
* c.f. [L$_2$ regularisation](ma/l2-regularisation.md), which aims to *make the weights smaller*