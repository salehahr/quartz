---
title: (Markley 2014) Fundamentals of Spacecraft Attitude Determination and Control
date: "2021-08-17"
external_url: "http://www.springer.com/de/book/9781493908011"
tags:
  - -resources/-bibliography
  - -sa/processed
  - -resources/-bibliography/bib-skimmed
  - -published
---

**Authors**: FL Markley, John Crassidis  
**DOI**: 10.1007/978-1-4939-0802-8

## Note/Nomenclature:

*   This book interpetes rotations/transformations in the [passive/alias](math/rotations/active-passive-or-alibi-alias-transformations.md) sense (I'm not a fan)
*   Quaternions in JPL [conventions](studienarbeit/quaternion-conventions.md) instead of Hamiltonian (not a fan of this either...)
*   Rotation matrix = attitude matrix

## Introduction

*   Attitude determination: memoryless approach without using statistics
*   Attitude estimation: approaches with memory, uses statistical info from a series of measurements
    *   filter approaches
    *   uses a dynamic motion model of the object

## Quaternions
* [Quaternion conventions](quaternion-conventions.md)
* [Quaternion multiplication](math/rotations/quaternion-multiplication.md)

## Rotations
"Euler's theorem:  any rotation is a rotation about a fixed axis"

[orientation-parametrisations](studienarbeit/orientation-parametrisations.md)
* [Euler axis/angle representation](math/rotations/euler-axis-angle-representation.md)
* [Rotation vector representation](rotation-vector-representation.md)
* [Gibbs / Rodrigues parameter representation](math/rotations/gibbs-rodrigues-parameter.md)
* Modified Rodrigues parameters

[Rotation error representation](math/rotations/rotation-error-representation.md)

## Filtering
* [Which orientation parametrisation to choose?](math/rotations/20.4-which-orientation-parametrisation.md)
* [Additive quaternion filtering](studienarbeit/50.4.1-additive-quaternion-filtering.md)
* [Error-State Kalman Filter](studienarbeit/50.5-error-state-kalman-filter.md) / [multiplicative-quaternion-filtering](studienarbeit/50.4.2-multiplicative-quaternion-filtering-mekf.md)
* [Observation-of-the-error-state-filter-correction](studienarbeit/50.7.1-observation-of-the-error-state-filter-correction.md)
* [H-jacobian-matrix-in-the-eskf-filter-correction](studienarbeit/50.7.1.1-h-jacobian-matrix-in-the-eskf-filter-correction.md)
* [ESKF reset](studienarbeit/50.7.3-eskf-reset.md)

