This is an unbiased estimate of the [[Performance indices]] that can be computed from the training set:


## Mathematics
![[Pasted image 20220716164331.png]]
noise + RSS + adjustment term

The first term is performance degradation due to noise. The second term is [[RSS]]. The third term is a covariance between the data and the estimator.

In the training set, we use y to calculate the estimator, and such the SURE accounts for this fact.

the R_hat does not decrease indefinitely, but instead looks like the parabola we would otherwise see in the test.

## Notes
This allows us to perform online estimation! No need for [[Splitting of datasets]]