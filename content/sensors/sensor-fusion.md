---
title: Sensor fusion
date: "2021-09-29"
mathjax: true
tags:
  - -sa/processing
  - sensors
  - -definitions
---

**Source**: [Phil's Lab](bibliography/phils-lab-sensor-fusion.md)

## Definition
Combine multiple sensor readings to form an improved estimate of a desired variable.

## Why sensor fusion?
* Overcome limitations of individual sensors (noise, uncertainty)
* Estimate quantities that are not directly measurable  
	e.g. gyroscope measures angular rates of change
	but can't directly measure roll and pitch angle

## Fusion in IMU
* Accelerometer only: good estimate in non-accelerating conditions
* Gyroscope only: good estimate over short periods of time (due to integration of bias terms)