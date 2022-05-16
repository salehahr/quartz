---
title: Thesis outline
date: 2022-03-11
tags:
  - ma
aliases:
- /thesis
---


# Thesis outline

1. Introduction
    1. Motivation
        * Minimally invasive surgery, sensor-aided to reduce time
        * Need for positional information + sensor data
        * Localisation requires map creation, requires feature extraction
    2. Problem statement
        * Deformable bladder, graphs instead of point features
        * Existing framework has high latency --> **replace with NN-based framework**
        * **Dimensionality problem**
    3. Contributions and outline
        * Main contribution: implementation of `NodesNN` and `EdgeNN`, combination schemes
        * Minor contribution: optimisation of `EdgeNN`
3. Background - Neural networks (general)
    * General:
        * input data --> (model(params)) --> output
        * loss = norm(output - ground truth label)
        * DNN = ML task with automatic feature extraction (no manual feature engineering)
    * Classification task if the outputs are discrete classes
        * Probability distributions: Bernoulli, multinoulli
        * Kullback-Leibler divergence, cross entropy
4. Background - Graphs (implementation-specific)
5. Network architecture
6. Results