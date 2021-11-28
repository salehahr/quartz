---
title: data-representation
date: 2021-11-27
tags:
  - machine-learning
---

**Parent**: [Data in ML](ma/data-in-ml.md)


**Source**: [google-ml-course](bibliography/google-ml-course.md)

> Good ML relies on good data.

# Data representation

* Feature engineering: extracting features from raw data
* Features: data that is readable or workable on by the ML algorithm

## Good features
* Should appear with non-zero values sufficiently often enough within the dataset (i.e. is actually useful enough to classify a lot of data points in the dataset and not just overly specific to sevveral data points only)
* Have clear and obvious meaning (e.g. meaningful units)
* No weird values, like negative seconds
	* To deal with missing values, create a boolean feature, then replace the missing value in the original feature
		* Discrete variables: add a new value to the set and use this to indicate a missing feature value
		* Continuous variables: use the mean of the feature data to ensur that the missing values do not affect the model
* Feature values shouldn't change over time (this can happen if the features come from a changeable model, e.g. assign categories based on clusters which can change)
* No extreme outlier values --> cap these out or transform/normalise the features

## Good practice
* Visualise the data (plots, histograms, etc.)
* Debugging (look for duplicates, NaNs, outliers, etc.)
	* Are training data and validation data similar?
* Monitor the data over time (data sampled yesterday as good as those sample today?)

All these to ensure the stability of the features over time.

## Methods
* [Scaling features](ma/scaling-features.md)
* [Binning](ma/binning.md)
* Scrubbing: remove bad data points
	* Omitted values
	* Duplicates
	* Bad (wrong) labels
	* Bad feature values (too much of an outlier)
* [Synthetic features (feature crossing)](ma/feature-crossing.md)