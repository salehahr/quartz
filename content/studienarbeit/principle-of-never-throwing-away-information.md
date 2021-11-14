---
title: Principle of never throwing away information
date: "2020-08-27"
tags:
  - -sa/processed
---

Source: [rlabbe](studienarbeit/rlabbe-kalman-bayesian-filters-in-python.md)

"Two sensors are better than one, even if one is less accurate than the other."

## Example 1
Given:

*   A: a more accurate sensor
*   B: a less accurate sensor

Should we therefore choose A as the estimate and discard B?
No, because B can improve our knowledge when combined with A.

![ScreenClip.1.png](./_resources/Principle_of_never_throwing_away_information.resources/ScreenClip.1.png)

Using the measurements from B further narrows the range of estimates (overlap between the error bars).

## Example 2
Assume:

*   Scale A has an error of +- 1kg
*   Scale B has an error of +- 9 kg

We measure:
A = 160 kg
B = 170 kg

![ScreenClip.png](./_resources/Principle_of_never_throwing_away_information.resources/ScreenClip.png)

Even though B is highly inaccurate, it still helps to narrow down the range of estimates.

