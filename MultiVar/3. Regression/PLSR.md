## Partial Least Squares Regression

	Regression taking into account covariance between X and Y


That is, we find structures in the latent variables that correlate with Y

In other words, reduce the influence of X-variations that do not correlate with Y-variation


	PLS aims to maximize the covariance between X and Y


We usually require fewer factors compared to [[PCR]], however if all the variance in X is relevant for Y, then there will likely be no difference


## Geometrically
![[multivar_plsr_ideal_case.png]]


To find the PLS relations, we take:

1. [[PCA]] of XTY (XTY is the covariance between X and Y)
2. [[PCA]] of Y

Combine the two into the "PLS inner relation"


## Solving by [[NIPALS]]
![[Pasted image 20220717223346.png]]


## Mathematical formulation
![[Pasted image 20220717223823.png]]
![[Pasted image 20220717223923.png]]





This is a latent variables regression which maximizes the covariance between X and Y. The ideal case would look something like the figure bellow. PCR still has the problem of not taking care between correlations in the outputs, and moreover correlations between inputs and outputs. The components used for PCR are based on [[Correlation]] structures in the X matrix, but nothing says they will be relevant for predicting Y. PLSR solves that, and also identifies structures in X which relate to the outputs.



#### Mathematical Formulation
Mathematically we start by calculating a covariance matrix between X and Y 
