---
title: ml-terminology
date: 2021-11-27
tags:
  - machine-learning
  - -definitions
---

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# ML Terminology
| Term          | Symbol                                                         | Description                                           |
| ------------- | -------------------------------------------------------------- | ----------------------------------------------------- |
| Output, label | $\mathbf{y}$                                                   | Variable to be predicted                              |
| Features      | $\left\lbrace \mathbf{x}_1, \dots, \mathbf{x}_n \right\rbrace$ | Representation of the (input) data                    |
| Model         | $f: \mathbf{x} \rightarrow \mathbf{y}'$                        | Mapping of the input to the predictions $\mathbf{y}'$ |
| Weights       | $\mathbf{w}$                                                   | Parameters of the model                                                      |

| Term            | Description                                                                                                                                 |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| Training        | Process of determining the model parameters (weights) that will allow an accurate mapping of the input to the resulting output (prediction) |
|                 | i.e. so as to minimise the loss                                                                                                             |
|                 | (empirical risk minimisation)                                                                                                               |
| Inference       | Applying the already trained model to a set of inputs without known labels                                                                  |
| Regression      | Prediction of continuous values                                                                                                             |
|                 | s. [simple regression  model](ma/simple-regression.md)                                                                                         |
| Classification  | Prediction of discrete values (classes)                                                                                                     |
| Loss            | Difference between prediction and actual output                                                                                             |
|                 | Penalty for a bad prediction                                                                                                                |
| Hyperparameters | Configuration settings for tuning how the model is trained                                                                                  |
