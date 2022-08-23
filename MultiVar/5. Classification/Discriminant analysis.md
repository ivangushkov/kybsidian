

## Overview
Linear and [[PLS]] analysis
* Recognition
* Discrimination
* [[Classification]]
* [[Clustering]]
	* How many groups are there?

Python: Sklearn

## Linear DA
Benchmark. Always use this as a baseline for anything else.

Two hypotheses
Gaussian assumption on X, **different means, same covariance** - homoskedasticity.
	I.e. measuring something different, but with the same sensor noise
Y is either 0 or 1 

LDA: Separate dataset s.t. unknown Y can be found with new X.
Separate = split the n dimensional room that X lives in into discrete areas.

Classify new samples with log-likelihood ratio hypothesis test:
	if  wTx greater than c, class 1, else class 0.
	i.e test which gaussian fits best with the new sample
	this test is a line, i.e. linear, due to the assumptions above.

This line: Maximizes the distinction for the two distributions when projecting down orthogonally from the line. This is achieved by tuning the *c* value.

**This is extendable to N-classes problems!** (Pairwise)

## Quadratic DA
When covariance are different, ratio becomes quadratic (No cancellations) 
Similar results to QDA when deploying [[feature engineering]] + LDA


## Partial Least Squares DA
Uses [[PLS]] since it takes into account the [[Correlation]] in X **AND** Y. (Esp categorical variables in Y). This makes it superior to LDA and [[Logistic regression]] in **multivariate cases**.

Uses one-hot encoding

Strategy:
1. Compute estimate of Y from Y
2. train the map from X to the estimate of Y
3. when there is an xi to be tested, compute estimate yi
4. Check which elements of estimate yi are close to 1
5. from these, reconstruct yi

Pros:
Gives maps of scores and loadings, which means PLSDA is **interpretable**
Inherits outlier detection frm PLS
Returns continuous values.

Challenges: 
What if output is about 0.5?
Need to select amount of factors == model order selection problem



