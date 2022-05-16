---
title: naive-probability
date: 2022-05-12
tags:
  - math/probability-theory
  - -definitions
---

# Naive probability

**Source**: [blitzstein-hwang](bibliography/blitzstein-hwang.md)

Let [event](definitions/event.md) $A \subseteq \Omega$
$$
P_\text{naive}(A) = \dfrac{|A|}{|\Omega|}
$$
where $|A|$ is the number of elements ([outcomes](definitions/outcome.md) in $A$).

## Required assumptions
* The [sample space](definitions/sample-space.md) $\Omega$ is finite.
* The [outcomes](definitions/outcome.md) $\omega \in \Omega$ have equal probability of happening each.

## Usage
* Problems with equally likely outcomes.
* Problems with symmetry $\rightarrow$ equally likely probabilities for all outcomes  
    e.g. flipping a fair coin
* As a *null model* (as a hypothesis)