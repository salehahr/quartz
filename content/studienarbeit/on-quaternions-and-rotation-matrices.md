---
title: On quaternions and rotation matrices
date: "2021-03-15"
external_url: "http://stackoverflow.com/questions/8919086/why-are-quaternions-used-for-rotations"
tags:
  - to-do/orphan
  - math
  - math/quaternions
  - -sa/to-be-processed
---

<http://stackoverflow.com/questions/8919086/why-are-quaternions-used-for-rotations>

It's worth bearing in mind that all the properties related to rotation are not truly properties of Quaternions: they're properties of Euler-Rodrigues Parameterisations, which is the actual 4-element structure used to describe a 3D rotation.
Their relationship to Quaternions is purely due to a paper by Cayley, "On certain results related to Quaternions", where the author observes the correlation between Quaternion multiplication and combination of Euler-Rodrigues parameterisations. This enabled aspects of Quaternion theory to be applied to the representation of rotations and especially to interpolating between them.
You can read the paper here: <http://archive.org/details/collmathpapers01caylrich> . But at the time, there was no connection between Quaternions and rotation and Cayley was rather surprised to find there was:

> In fact the formulae are precisely those given for such a transformation by M. Olinde Rodrigues Liouville, t. v., "Des lois géométriques qui régissent les déplacements d'un système solide \[...\]" (or Comb. Math. Journal, t. iii. p. 224 \[6\]). It would be an interesting question to account, a priori, for the appearance of these coefficients here.

However, there is nothing intrinsic about Quaternions that gives any benefit to rotation. Quaternions do not avoid gimbal lock; Euler-Rodrigues parameterisations do. Very few computer programs that perform rotation are likely to truly implement Quaternion types that are first-class complex mathematical values. Unfortunately, a misunderstanding of the role of Quaternions seems to have leaked out somewhere resulting in quite a few baffled graphics students learning the details of complex math with multiple imaginary constants and then being baffled as to why this solves the problems with rotation.

