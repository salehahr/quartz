---
title: Particle filters
date: "2020-08-23"
tags:
  - SLAM/filter-vs-optim/filter-based
  - -sa/processed
---

Parent: [Filter localisation methods](filter-localisation-methods.md)

Source: [Wikipedia Lokalisierung](wikipedia-lokalisierung.md)
Particle filter / Monte Carlo localisation / sequential Monte Carlo methods

*   allow solution of all three localisation problems
*   POSE represented by a particle cloud
*   Each particle : possible POSE
*   The filter checks the plausibility of each particle
    *   Increases and decreases the probabilities of each particle accordingly
    *   When a lower probability threshold is exceeded, the particle is not considered any longer

Source: [Scaradozzi 2018 SLAM application in surgery](scaradozzi-2018-slam-application-in-surgery.md)
**Particle filters (sequential Monte Carlo)**

*   Posterior representation: particles (set of random state samples)
*   Suitable for implementation with any probabilistic robot model with Markov chain formulation
*   Easy to implement
    *   no need to linearise
    *   closed-form solutions of the conditional probability are irrelevant (as in KF)
*   Poor performance in higher dimensional spaces

*   Rao-Blackwellized particle filters
    *   more efficient solutions, however, prone to significant estimation inconsistencies
    *   therefore, as estimation consistency is quite important, led to the adoption of different sampling strategies
*   FastSLAM
    *   integrates particle filters and EKF
        *   particles filters for estimating robot path
        *   for each particle, EKF for estimating feature locations
    *   mapping problem split
        *   one mapping problem for each feature in the map
    *   particle approximation doesn't converge uniformly in time

