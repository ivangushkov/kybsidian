## Intuition
There exists an "ideal" PDF that generates the data. We try to model this PDF. 

We would like the ideal world to match the statistical world.  

Using the [[Kullback-Leibler divergence]], we can find a measure of the difference between these two wrt to a measure that **we do not know**. (p0). Note that l is the log likelihood.
![[Pasted image 20220716164853.png]]

## Akaike's Information criterion
Since we cannot compute KL wrt p0, we instead estimate it!

AIC yields
![[Pasted image 20220716165013.png]]

We find the theta that minimizes the model order of two terms, the first one being the log likelihood loss ([[maximum likelihood estimation]]) and a correction term that makes AIC unbiased.

AIC reduces to [[maximum likelihood estimation]] when we remove n and the second term!


This method again also uses **just the training set!** No need for [[Splitting of datasets]] other than for testing real world performance.


## Other flavors
The second adjustment term can be altered to achieve different results, like punishing model complexity. Bayesian IC and AIC are the most used


## Problems
At the end of the day, we can only estimate the KL, and such we may be prone to overfit to the training

Just selecting the minima automatically may lead to a non-parsimoneous model, so again we need to use our own brainz to figure this out.


	More data leads to larger models for AIC

	AIC in general picks larger models compared to BIC

	AIC tends to give better performance


Parsimony consideration: is the AIC performance desirable when having more parameteters and less interpretability?
