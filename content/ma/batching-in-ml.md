---
title: batching-in-ml
date: 2021-11-27
tags:
  - machine-learning
---

**Parent**: [Data in ML](ma/data-in-ml.md)  
**See also**: [Batch](definitions/batch.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)  

Large batches of data
* result in a long computation time of a single iteration
* possibly contain [redundant](ma/redundancy-in-ml.md) data

Hence, this results in [variations](ma/variations-gradient-descent.md) of the classic [gradient descent](ma/gradient-descent.md), which performs calculation over the whole dataset per iteration.
