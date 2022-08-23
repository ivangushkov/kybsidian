## Linear Discriminant Analysis

Between two classes. Should be a baseline, like how [[MLR]] should be the baseline for neural networks.

### Assumptions
probability dists for both classes are gaussian
The means are different but the variances are the same (i.e. homo[[Skedacity]])
The moments can be estimated from the training set


	Can be interpreted as measuring two things with the same sensor that 
    yields the same noise
	
![[Pasted image 20220720220748.png]]


	LDA: How do we separate the space that these live in?

## Graphical intuition
We are trying to find a line that yields projections on a normal to the line that maximizes the separation between the distributions on the normal of the two classes.

![[Pasted image 20220720221512.png]]

This is a connection to [[PCA]] since the goal is to maximize the **between-class variance** s.t. the in-class variance is reduced.


### Classifying
We can classify a new sample x using a log-likelihood ratio hypothesis test. I.e. we take the log likelihoods for both classes. If we get above a threshold, it is the sample belongs to the numerator, if not the denominator.


