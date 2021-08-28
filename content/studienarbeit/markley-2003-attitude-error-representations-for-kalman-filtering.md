---
title: Markley 2003 Attitude Error Representations for Kalman Filtering
date: "2021-08-16"
tags:
  - -resources/-bibliography
  - -resources/-bibliography/bib-to-read
  - -sa/to-be-processed
---

Source: [http://scholar.google.com/scholar?cluster=9266330323139560128&hl=en&as\_sdt=0,5](http://scholar.google.com/scholar?cluster=9266330323139560128&hl=en&as_sdt=0,5)
Author: FL Markley

Motivation

*   Quaternion as an attitude representation
    *   Good: lowest dimensionality while being a globally nonsingular representation
    *   Not so good: must obey a unit norm constraint

*   In research, various methods for either getting around the norm constraint, or to enforce it
*   Most successful method employs the global attitude as a unit quaternion with a 3-comp attitude error representation

*   MEKF doesn't estimate the quaternion state. Instead, it estimates the 3-comp error, with the quaternion as a reference about which the errors are defined

**Structure of the paper**

*   Attitude representations
*   Alternative quaternion estimation schemes
*   Basic MEKF equations
*   Second order attitude filter

Contents/Chapters
Takeaway

