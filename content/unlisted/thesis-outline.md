---
title: Thesis outline
date: 2022-03-11
tags:
  - ma
---

# Outline

1. Introduction
	* Motivation
		* Problem to be solved (overall)
			* BCS takes too long
			* Especially tissue identification (cryosection)
			* Bypass time-consuming cryosection, incorporate sensors
		* Why do we need sensor localisation for that
			* Sensor data is only useful with positional information --> need for localisation of the sensor measurements
	* Problem statement
        * functions take too long
		* Deformable -- bad for typical point features (examples ORB, etc.)
	* Contributions
	* Outline
1. Literature/State of the art/Theory
	* U-Net
	* VGG16
1. Methods/Experiments  
    1. Training data generation
    2. Split task into three networks
        1. Network 1: filtering/segmentation/skeletonisation
        2. Network 2: node extraction
        3. Network 3: adjacency matrix determination  
           Two methods:
           1. Combinatorial method
           2. Brute force method
1. Misc topics
	1. **Tuning/Hyperparameter optimisation**, wandb framework for automating this
	2. Domain knowledge for modifying VGG16 for edge extraction
	3. Effect of batch size
	4. Constructing the training/validation data (codifying of node types etc, ratio of adj/non-adj nodes)
	5. Wie angepasst (the networks)
	6. Data augmentation
2. Results
3. Conclusion