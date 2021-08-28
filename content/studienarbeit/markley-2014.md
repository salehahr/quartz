---
title: (Markley 2014) Fundamentals of Spacecraft Attitude Determination and Control
date: "2021-08-17"
external_url: "http://www.springer.com/de/book/9781493908011"
tags:
  - -resources/-bibliography
  - -sa/processed
  - -resources/-bibliography/bib-skimmed
---

Authors: FL Markley, John Crassidis
**DOI**: 10.1007/978-1-4939-0802-8

Note/Nomenclature:

*   This book interpetes rotations/transformations in the [passive/alias](passive_alias.md) sense (I'm not a fan)
*   Quaternions in JPL [convention](convention.md) instead of Hamiltonian (not a fan of this either...)
*   Rotation matrix = attitude matrix

Introduction

*   Attitude determination: memoryless approach without using statistics
*   Attitude estimation: approaches with memory, uses statistical info from a series of measurements
    *   filter approaches
    *   uses a dynamic motion model of the object

Quaternions
[Quaternion conventions](quaternion-conventions.md)
[Quaternion multiplication](quaternion-multiplication.md)

Rotations
"Euler's theorem:  any rotation is a rotation about a fixed axis"

[Euler axis/angle representation](euler-axis_angle-representation.md)
[Rotation vector representation](rotation-vector-representation.md)
[Gibbs / Rodrigues parameter representation](gibbs-_-rodrigues-parameter-representation.md)
Modified Rodrigues parameters

[Rotation error representation](rotation-error-representation.md)

Filtering
[Which orientation parametrisation to choose?](permanent/20.4-which-orientation-parametrisation-to-choose.md)
[Additive quaternion filtering](additive-quaternion-filtering.md)
[Error-State Kalman Filter](error-state kalman-filter.md) / [multiplicative-quaternion-filtering](multiplicative-quaternion-filtering.md)

*   [Observation of the error state](observation-of-the-error-state.md)
*   [H Jacobian matrix in the ESKF filter correction](h jacobian matrix-in-the-eskf-filter-correction.md)

[ESKF reset](eskf-reset.md)

