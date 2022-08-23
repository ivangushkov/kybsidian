## Overview
Classification with a continuous output between 0 and 1. Sort of a continuous version of [[Discriminant analysis]].

Uses a "logistic function" to model a binary dependent variable (i.e. class 1 or 2 )
![[Pasted image 20220720222109.png]]

	Logistic regression is finding the parameters of the function that 
    best splits the binary variable.


If we want to estimate the prob. of something happening, we need to use this instead of [[LDA]]. The more the assumptions hold, the better the method is

### Assumptions
The probabilities of the outcomes can be modelled as a linear relationship wTx + c.
![[Pasted image 20220720222459.png]]

w and c need to be learnable from the training set


## Interpretation
The classifier returns a probability that an event is a certain class.