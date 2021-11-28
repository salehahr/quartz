---
title: embeddings
date: 2021-11-28
tags:
  - machine-learning
---

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Embeddings

* Translate a high dimensional vector into a lower dimensional space (embedding)
* e.g. representing words by sparse vectors
* Ideally, similar inputs are grouped close together in the embedding space (similarity metric)

## Learning embeddings from data
* Embedding layer: a hidden layer with $D$ nodes, where $D$ is the dimension of the embedding space
* Each of these dimensions is called a **latent** dimension due to it being inferred from the data
* This hidden layer learns how to cluster the data to optimise the metric we have chosen
* Weights between the the input and the embedding layer are the coordinate values of the input within the embedding space
* Hyperparameter: how many [embedding dimensions](ma/embedding-dimensions.md) $D$?


## Techniques for reducing dimensionality
* Principal component analysis

## Example 1
2D embedding for movies:  
![](/_img/movies-2d-embedding.png)

Each movie is a point in the 2D space.

Input representation: movies watched by different users  
![](/_img/embedding-movies-user-input.png)

For the bottom user: a dense input representation could be
$$ \left[\begin{array}{cccc cccc}
0 & 1 & 0 & 1 & \dots & 0 & 0 & 1
\end{array}\right] $$

For millions of movies, it would be inefficient to list out all of the unwatched movies --> preprocess the input

### Preprocessing
1. Build a dictionary mapping each feature to an integer (coding of the movies).  
2. Now the user input vector can be the sparse representation  
	$$\left[\begin{array}{ccc}
	1 & 3 & 999999
	\end{array}\right]$$
	
### Training data
If the user has watched 10 movies:
* Take 3 as inputs
	* Fed through the embedding layer etc int the neural network
	* Comes out on the logit layer as a prediction for which movies the user would like
* Take 7 as ground truth training labels (for loss calculation)

![](/_img/embedding-movies-nn.png)

### Geometric view
![](/_img/embedding-weights-coordinates.png)
	
## Example 2
Predicting home sales prices  
![](/_img/embedding-house-prices-nn.png)

* What is the size of the house from the set of words? 'Roomy', 'spacious', etc.
* We reduce the high dimensional input vector to the lower dimensional 3D space of house size categories
* Loss is between predicted price and actual sale price