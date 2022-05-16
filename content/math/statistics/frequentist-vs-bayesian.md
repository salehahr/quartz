---
title: Frequentist vs Bayesian statistics
date: "2020-08-31"
tags:
  - -definitions
  - -sa/processed
  - math/statistics
  - math/probability-theory
---

# Frequentist vs Bayesian statistics

**Sources**: [rlabbe](bibliography/rlabbe.md), [blitzstein-hwang](bibliography/blitzstein-hwang.md)


## Frequentist
* Probability represents the frequency over an experiment repeated infinitely many times
* Probability of flipping a fair coin infinitely many times is 50%

## Bayesian
* Probability represents a *belief* about the event [[bh](bibliography/blitzstein-hwang.md)]
    * $\hat{=}$ hypothesis
    * e.g. probability that someone is guilty
* Probability of flipping a fair coin one more time: which way do I believe it landed? [[rlabbe](bibliography/rlabbe.md)]
    *  Bayesian statistics takes past information (prior) into account
    *  If finding the prior is tricky, frequentist techniques are sometimes used

## Example
e.g. Weather

*   Frequentist: If it rains 4 out of 100 days, the chance of rain today is 25%
*   Bayesian: If we know that it's raining today and the storm front is stalled (prior information), it is likely to rain tomorrow
