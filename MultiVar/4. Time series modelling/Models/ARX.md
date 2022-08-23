Disturbance only enters as a single additive term

We have y's and u's backwards in time
![[Pasted image 20220719095740.png]]

This can be taken to discrete frequency domain using the Z-transform:
t-n = q^-n


The block diagram yields

![[Pasted image 20220719100008.png]]

While we can change the coeffieients for u and e, the modes (poles) are the same, meaning that we do not have flexibility to alter the steady state for u vs e.

From a [[Bias variance tradeoff]] we have less variance / less complexity by sharing modes


Given the previous data and a theta estimate, we can immediatly calculate the forecast, and can be written as 

y = thetaT * u

The full model can thus be stated as 

y = theta * u + e

And we saw that if e is iid gaussian, then [[Least squares]] is the [[maximum likelihood estimation]] solution!!!

	Thus, ARX makes our lives easier