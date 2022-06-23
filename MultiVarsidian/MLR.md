## Multiple Linear Regression
Using notes in OneNote to revise, return later (CHRISTOPHER MAYBE SAVE??)

MLR assumes no error in X, the OLS assumption.

#### Practical Considerations

MLR might struggle when we have correlations in the data. In orthogonal cases it will perform well, but we might lose some causality because the MLR gets confused by the correlations. Take the example of the Degree of Cerosis modelled by some variables, male and female and Alcohol consumption included. Since men drink a lot more there is a correlation between the X variables M/F and Alcohol Consumption. Then the MLR might pick up on that the most and capture most of the effect of alcohol in the MF variable. A beta medical researcher then will look at these results and discard the AC variable, assuming the MF is the real cause. Causality might get lost. This leads to the need to use latent variables regression methods. Clearly here there is no real variability of M/F, it is simply another expression of the AC feature which is the real factor. There is a need for dimensionality reduction which will recognize that M/F is just correlated with AC.