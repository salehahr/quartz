---
title: Expected value
date: "2020-08-27"
tags:
  - to-do/to-clarify
  - -sa/processed
  - math/statistics
  - math/probability-theory
---

**Parent**: [Probability theory](math/statistics/probability-theory.md)

# Expectation

**Source**: Bishop

## Definition
$$
\begin{alignat}{3}
\mathbb{E}[X] &= \sum_{x \in X} x \cdot P(x)
    &&\qquad \text{discrete}\\
&= \int_{X} x \cdot p(x) ~ \text{d}x
    &&\qquad \text{continuous}
\end{alignat}
$$

## Approximation
Given a finite number of $N$ points drawn from the probability distribution, $\mathbb{E}$ can be approximated by
$$
\mathbb{E}[X] \approx \dfrac{1}{N} \sum_{n=1}^N X(\omega_n)
$$


----

**Source**: [rlabbe](bibliography/rlabbe.md)

## Example
* If we take a thousand sensor readings, the readings won't always be the same (due to the inherent noise).
*   The expected value 'averages' all of the readings into a single value.
*   This can be a mean (probabilities of all values assumed equal)
*   Or if incorporating individual and different probabilities, the expectation isn't the mean of the range of values

$$
\begin{alignat}{3}
\mathbb{E}[X] &= \sum_{i=1}^n p_i x_i
    &&\qquad \text{discrete}\\
&= \int_{a}^b x f(x) ~ \text{d}x
    &&\qquad \text{continuous}
\end{alignat}
$$

**Proven**: the average of a large number of measurements will be very close to the actual weight
- [ ] What is the name for this theorem?

## Summary
*   Using a normal mean calculation assumes that all measurements are equally likely (assumption of equal probability).
*   However, real sensors tend to return readings close to the actual value (barring any offset disturbances).
*   They can still return readings further away from the actual value, just with a reduced probability compared to values nearer the actual value
*   The [probability distribution](studienarbeit/probability-distribution.md) must be factored in somehow