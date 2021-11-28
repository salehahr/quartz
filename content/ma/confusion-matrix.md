---
title: confusion-matrix
date: 2021-11-28
tags:
  - machine-learning
---

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Confusion matrix
* $N \times N$ matrix which shows how successful the classification model's predictions were.
* $N$: number of classes, e.g. $N=2$ for true/false classes
* Axes: predicted class/label, actual class/label

|              | Predicted True | Predicted False |
| ------------ | -------------- | --------------- |
| Actual True  | TP             | FN              | 
| Actual False | FP             | TN              |

In multi-class classification, the confusion matrix can help to identify mistake patterns—does the model tend to mistakenly predict a certain class for another?