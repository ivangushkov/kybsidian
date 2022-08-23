## Measures
Using [[PCA]] to eliminate outliers

#### Leverage
The distance between a sample and the model mean (in the model space)

Samples further away have more leverage, which means that a perturbation causes a relatively larger change in the model than a sample with less leverage. 

	Removing a sample with more leverage thus affects the model more

#### Residual
The distance between a sample and the reprojected sample through the model


## Cause of outliers
* Measurement error
* Wrong labelling
* Deviating products / processes
* Noise
* Extreme / interesting samples


## Detection

#### Hotellings T^2
A multivariate generalization of the t-test. It represents the impact of one component relative to the sum of all.

![[Pasted image 20220714003022.png]]


#### Leverage
Closely related to Hotellings. 
![[Pasted image 20220714003157.png]]

Calculate how much variance is in a sample relative to all the variance.

From this we can calculate a critical limit for leverage, which equals three times the average leverage.


#### Plots

From the variance in the sccore vectors, a confidence ellipse can be drawn in the 2D score space.

Ellipse = Variance of the score vectors multiplied by the critical limit.

	Do not blindly remove all samples outside a limit, but explore if 
    they are part of another cluster


## X-residuals
That part of the data that has not been modeled.

Data = information + noise. Therefore, the X-residual is a measure of the noise after A PCs have been taken into account
![[Pasted image 20220714003606.png]]


which leads to an equation for error for each sample:
![[Pasted image 20220714003631.png]]


## Q-residuals
The square of the X-residual, with a corresponding critical value.

## F-residuals
The square root of the Q-residuals divided by the number of variables. Compare for significance against the standard F-test hypothesis for a chosen significance level.


## Influence plot
Comparing either Hotellings or Leverage vs F or Q residuals

	High F or Q means that the model does not explain the sample well.

	High Hotellings or Leverage means that the sample has a very high 
    influence on the model