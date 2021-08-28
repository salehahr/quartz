---
title: scipy.optimize
date: "2021-08-26"
external_url: "http://stackoverflow.com/questions/52438263/scipy-optimize-gets-trapped-in-local-minima-what-can-i-do"
tags:
  - -sounding-board
  - -sa/processing
---

<http://stackoverflow.com/questions/52438263/scipy-optimize-gets-trapped-in-local-minima-what-can-i-do>

Local optims sensitive to initial value.
Workarounds:

*   use your optimization in a loop with random starting points inside your boundaries
*   use an algorithm that can break free of local minima, I can recommend scipy's basinhopping()
    It repeats your minimize procedure multiple times and get multiple local minimums. The minimal one is the global minimum.
    
*   use a global optimization algorithm and use it's result as initial value for a local algorithm. Recommendations are NLopt's DIRECT or the MADS algorithms (e.g. NOMAD). There is also another one in scipy, shgo, that I have no tried yet.

[http://scipy-lectures.org/advanced/mathematical\_optimization/
- choosing-a-method](http://scipy-lectures.org/advanced/mathematical_optimization/
- choosing-a-method)

Without knowledge of the gradient:

*   In general, prefer BFGS or L-BFGS, even if you have to approximate numerically gradients. These are also the default if you omit the parameter method - depending if the problem has constraints or bounds
*   On well-conditioned problems, Powell and Nelder-Mead, both gradient-free methods, work well in high dimension, but they collapse for ill-conditioned problems.

With knowledge of the gradient:

*   BFGS or L-BFGS.
*   Computational overhead of BFGS is larger than that L-BFGS, itself larger than that of conjugate gradient. On the other side, BFGS usually needs less function evaluations than CG. Thus conjugate gradient method is better than BFGS at optimizing computationally cheap functions.

With the Hessian:

*   If you can compute the Hessian, prefer the Newton method (Newton-CG or TCG).

If you have noisy measurements:

*   Use Nelder-Mead or Powell.

