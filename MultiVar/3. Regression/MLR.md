## Simple Linear Regression
The precursor to MLR is simple LR, where we attempt to fit a line to data

One way of estimating this is the [[Least squares]] fit. 
* Total LS: Project down, when assuming x are noisy
* Ordinary LS: Move down in y-axis, assume no noise i x
![[Pasted image 20220716224937.png]]


## Multiple Linear Regression

Instead of one x and one y, we have many x and one y.
Instead of a line as in SLR, MLR yields a plane.

### Generalization
Multiple x multiple y! Regardless, we will still have linear relationships across the board.

Naive strategy: treat every yi as independent of eachother (i.e. a series of MP) since we may lose information!

[[PLS]] solves this problem!!

	MLR should be a baseline for all other methods!


## Practical problems
Solving MLR through the [[Least squares]] normal equations may lead to problems, like XTX not being invertible or close to noninvertible, or if they yield solutions outside of the hypothesis space

	The coefficients may not reflect the causality in the system, just 
    the correlation

If we have two variables (or more) that are correlated, then adding the second will only improve the model with information that is not explained already! This may be problematic, and it may be an indicator that MLR is not the correct tool for this job. For this we may deploy regression methods based on [[Latent variables]]






#### Practical Considerations

MLR might struggle when we have [[Correlation]]s in the data. In orthogonal cases it will perform well, but we might lose some causality because the MLR gets confused by the correlations. Take the example of the Degree of Cerosis modelled by some variables, male and female and Alcohol consumption included. Since men drink a lot more there is a correlation between the X variables M/F and Alcohol Consumption. Then the MLR might pick up on that the most and capture most of the effect of alcohol in the MF variable. A beta medical researcher then will look at these results and discard the AC variable, assuming the MF is the real cause. Causality might get lost. This leads to the need to use latent variables regression methods. Clearly here there is no real variability of M/F, it is simply another expression of the AC feature which is the real factor. There is a need for dimensionality reduction which will recognize that M/F is just correlated with AC.