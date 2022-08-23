# Bias-Variance tradeoff

This is a ubiquitous phenomenon in datascience, and one of the central topics of this course.


## Geometric Interpretation
The higher the model order, the higher the bias on the dataset, but the variance will increase as well. Why? Consider the interpretation that adding more features is like adding dimensions. We have some point in space. In order to reach it we might start spanning dimensions. We will get closer to it if we add more dimensions, reducing the bias, but our "guess" will land in a bigger neighbourhood around the point. The point might represent the true parameters. Since the higher we go in dimensions the more "space" we have per "unitary dimension", we might land around the point with a greater variance. The more complex the estimator map is, the more we amplify the noise in the measurements.


## Mathematical interpretation
The MSE can be decomposed into two terms, which end up being the sum of [[Variance]] and [[Bias]] squared.

That means that for a given MSE, we much choose between low variance and high bias, or high variance and low bias.

![[Pasted image 20220710211703.png]]
