## Partial Least Squares Discriminant Analysis
As we know, [[PLSR]] is  a linear regression from X to Y that takes into account the covariance between X and Y.


Now: How do we use this method when Y are categorical?

Main idea: Instead of using Y (qualitative), create a Ytilde that records the membership of each observation to an indicator variable. Example: 

![[Pasted image 20220720222944.png]]

This is sort of a one-hot encoding, and we can do [[PLSR]] as normal, i.e. train the map X -> Y_tilde

From this map, we map back elements that are "close to 1"

The "close to 1" or "close to 0" comes from how, when we project a new sample onto the model, we will not necessarily land right on zero. The PLSR training yields a line, which we use to project.
![[Pasted image 20220720223604.png]]


### Properties
Inherits everything from [[PLSR]]: Scores and loadings, outlier detections, estimates of parameter uncertainties, but has the ambiguity of y close to 0.5

Also requires solving a [[Model Order Selection]] problem, just like [[PLSR]]

[[Logistic regression]] is univariate, so since PLSDR can capture correlations in Y, PLSDR may perform much better in multivariate cases. For scalar y's however, [[Logistic regression]] works better, and feature-engineered [[LDA]] even better.
