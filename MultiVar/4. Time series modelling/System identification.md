
Disturbances cannot be controlled
Inputs can be controlled

modelling a dynamical system as $\dot y = f(y, u, \theta)$ makes the sysid definition:

> Estimate $\theta$ given noisy measurements of y and u


A model is as good as it can predict observed data!

	For LTIs, identifying the parameters is equivalent to determining 
    the impulse response!


## General approach
![[Pasted image 20220718174841.png]]



## Parametric, linear and time domain
[[Model Order Selection]] is done by defining the transfer function G, as in Y = GU, where G is K * num / den, both num and den are polynomials.

Selecting G is a **paramount** problem! We need to use our intuition of [[Poles and zeros]] to select the best order.


## Model selection

[[ARX]] may yield some crosscorrelation for e, so if this is problematic, switch to [[ARMAX]]