---
title: Probabilistic models for IMU
date: "2021-03-23"
tags:
  - -sa/processed
  - sensors/IMU
---

Parent: [IMU index](imu-index.md)
Source: [MKok 2017 Using inertial sensors for position and orientation estimation](mkok 2017 using inertial sensors-for-position-and-orientation-estimation.md)

Three main components to the probabilistic models

1.  [IMU measurement model](imu-measurement-model.md) (infer knowledge about pose from measurements) ![unknown_filename.5.png](./_resources/Probabilistic_models_for_IMU.resources/unknown_filename.5.png)
2.  [Prediction model](SLAM/prediction-model.md) (how sensor pose changes over time)
3.  Models of the initial pose (prior)

Knowledge we are interested in: pose of the sensor

*   time-varying variables: states ![unknown_filename.png](./_resources/Probabilistic_models_for_IMU.resources/unknown_filename.png)
*   constants: parameters ![unknown_filename.1.png](./_resources/Probabilistic_models_for_IMU.resources/unknown_filename.1.png)

Knowledge available to us: sensor dynamics, available sensor measurements ![unknown_filename.2.png](./_resources/Probabilistic_models_for_IMU.resources/unknown_filename.2.png)

Conditional probability distribution

*   Smoothing problem (uses all measurements)
    ![unknown_filename.3.png](./_resources/Probabilistic_models_for_IMU.resources/unknown_filename.3.png)
    
*   Filtering problem (only up to t-th measurement)
    ![unknown_filename.4.png](./_resources/Probabilistic_models_for_IMU.resources/unknown_filename.4.png)
    Parameters are treated as slowly time-varying —> incorporated into state vector x
    
*   Variations: fixed-lag smoothing, MHE

Assumption: our models have the [Markov property](markov-property.md)

The complexity of pose estimation can be mainly attributed to

*   the nonlinear nature of orientation —> [linearise the orientations](linearise-the-orientations.md)
*   the different available ways of [parametrising orientation](parametrising-orientation.md)

Resulting probabilistic models
Pose estimation
![unknown_filename.6.png](./_resources/Probabilistic_models_for_IMU.resources/unknown_filename.6.png)
![unknown_filename.7.png](./_resources/Probabilistic_models_for_IMU.resources/unknown_filename.7.png)

Initial conditions
![unknown_filename.8.png](./_resources/Probabilistic_models_for_IMU.resources/unknown_filename.8.png)
![unknown_filename.9.png](./_resources/Probabilistic_models_for_IMU.resources/unknown_filename.9.png)

Orientation at t=1 from QUEST algo
![unknown_filename.10.png](./_resources/Probabilistic_models_for_IMU.resources/unknown_filename.10.png)

Orientation estimation
![unknown_filename.11.png](./_resources/Probabilistic_models_for_IMU.resources/unknown_filename.11.png)
![unknown_filename.12.png](./_resources/Probabilistic_models_for_IMU.resources/unknown_filename.12.png)
![unknown_filename.7.png](./_resources/Probabilistic_models_for_IMU.resources/unknown_filename.7.png)

