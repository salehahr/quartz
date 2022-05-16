---
title: Probability mass function
date: 2022-04-29
tags:
  - math/probability-theory
  - -definitions
---

**Backlinks**: [Experiments in probability theory](definitions/probability-experiment.md)

# Probability mass function

**Source**: [Wiki](https://en.wikipedia.org/wiki/Probability_theory)

Each outcome $\omega$ in the [sample space](definitions/sample-space.md) $\Omega$ is assigned a probability value via the *probability mass function* $p(\omega)$ with the properties
$$
\begin{align}
p(\omega) &\in \left[ 0, 1\right] \quad \forall\, \omega \in \Omega\\
\sum_{\omega \in \Omega} p(\omega) &= 1
\end{align}
$$

---

**Source**: Yang

$X$ is distributed according to the distribution $P$,
$$X \sim P(x) ~.$$

For a specific instance of $X$ (or outcome), evaluating the pmf gives the probability
$$P(X = x_i) = P(x_i) = p_i \geq 0$$