---
title: sampling-data
date: 2021-11-27
tags:
  - machine-learning
---

**Parent**: [Data in ML](ma/data-in-ml.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Sampling data in ML
Three basic assumptions
1. Data points are drawn **independently and identically (i.i.d.)**, and **at random**, from the data distribution, i.e. the data points don't influence each other
2. The data distribution doesn't change over time (stationary)
3. The data is pulled from the same distribution, for both training and validation sets

Situations where these assumptions may be violated:
* change in user perception, therefore resulting in different labelling of a dataset
* change in population which result in new demographics or target market