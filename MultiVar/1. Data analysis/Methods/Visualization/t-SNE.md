## t-distributed Stochastic Neighborhood Embedding
A way to visualize structure of high dimensional data in 2 or 3 dimensions, like [[PCA]] but different

	t-SNE is a dimensionality reduction algorithm

Problem with PCA is that it will preserve "global structure" and such the following structure would NOT be preserved: 
![[Pasted image 20220721023219.png]]

Thus, the focus of t-SNE is to resolve local structure. To do this, we utilize a cost function for which points that are relatively distant in some metric have low impact on cost.

How to balance the attention between local and global aspects of the data is called "perplexity" and is essential to tune.

	The higher the perplexity, the more "local" means "global"

To get the most out of t-SNE:

	Analyze multiple plots!

	Classical mistake is finding patterns in noise

## Features
Stochastic (same data different init yields different outputs)
Nonlinear
Adapting to the underlying data - distance depends on local structures.
Normalization: The original data is mapped into some equalized domain, where just the local effects are represented.


## Problems
Ex:
	Crowding: How to map the corners of a 2D square onto a line?


## Prerequisites
t-distribution: The tails are heavier than the normal
[[Kullback-Leibler divergence]] for t-SNE:
For two discrete distributions of classes, P, and Q, we may have something like this: 
![[Pasted image 20220721022838.png]]
The KL of P, Q is then the sum of pi * log pi/qi

	We are weighing the pi with "how important qi is to pi"
Thus, KL is not symmetric

## Geometric intuition
For a point i, we create a gaussian around it. We can then ask "what is the probability that the point i would pick the point j as its neighbor" from the gaussian. The more points we have between i and j, the less likely we are to pick j as our neighbor!

	This probability is the "similarity measure"

The shape of the gaussian is the "global property" while the points between i and j reflect local properties 
![[Pasted image 20220721024208.png]]


This measure S has a dual in the lower dimensional space, S'. We wish to find S' that minimize the [[Kullback-Leibler divergence]] between the two 

## Algorithm
p is in the original space
q  is in the reduced space

1. Compute the p_ij
2. Find a set of y_i whose q_ij minimizes the [[Kullback-Leibler divergence]]



p depends on the gaussian we fit to the points, more specifically the sigma. Defining the sigma is what is meant by "perplexity"


## Results
KL divergence is asymmetric:
1. Mapping close points in high dim far away in low dim yields high cost
2. Mapping far points in high dim closeby in low dim does not yield high cost

This leads to local structure being preserved over global one.


t-SNE specifically uses Student t-distribution to compute the similarities between points in the low dimensional space:
1. Gets rid og exponential
2. Heavy tail helps with crowding.