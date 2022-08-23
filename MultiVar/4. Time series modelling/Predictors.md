Build y_hat for t given t-1


We have the relationship y = Gu + He

let v = He, s.t. v = y - Gu

From the u- and y- we can compute v- and forecast what will happen to noise (v_hat for t given t-1)

Compute y_hat for t given t-1:
![[Pasted image 20220719103939.png]]


	To build the forecast, we only need to forecast the noise, since Gu 
    is deterministic

The focus is then entirely on H


For [[ARX]], the predictor can be calculated directly, since the rhs of y is 1-A
For [[ARMAX]], the predictor is recursive and can thus not be calculated directly, since the rhs of y is C-A


Once we have the predictors we can then find theta

theta_hat = argmin (come cost as a function of y_hat). This is the workflow of [[PEM]]