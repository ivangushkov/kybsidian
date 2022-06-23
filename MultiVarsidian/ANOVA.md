## ANOVA

#### What is ANOVA?
ANOVA is connected to [[Multiple Linear Regression]] and [[least squares]]. In analyses the regression coefficients. Thus ANOVA is most useful for orthogonal designs, as MLR is an orthogonal method. ANOVA separates the data into contributions from structure and noise.

Data = Structure + Noise 
$SS_{total} =  SS_{model} + SS_{noise}$
Total Variation = Modelled Variation + Not Modelled Variation

Where SS = squared sum. ANOVA 

#### Contents of an ANOVA table
![[multivar_ANOVA_table_assignment7.png]]

##### Summary Section
The sum of squares for both error and model are given. The DoF are the number of parameters for the model and for the error the DoFs are the number of samples - model dof - 1 (mean centering). The MS (Mean Squares) is the SS normalized by the DoF (SS/DoF) and the F-ratio is the ratio between MS for model and MS for error
$F-ratio = \frac{MS model}{MS error}$

If the F ratio is big that means we have a real model. The p-value is calculated from the F-ratio and the DoFs for both model and error. The F-ratio and the P-value are 2 sides of the same coin which is estimating model significance.

##### Variables Section
The variables section gives similar information as the summary, but decomposed into the different variables. Here the p-values can be used to evaluate if a variable is significant for the model, or if it can be excluded.

#### Lack of Fit Section
The SS of the residuals has contribution from the so called SS of pure error and the SS due to lack of fit. The SS of pure error is the SS of the replicates about their mean. Here the replicates will be experiments with the same parameters. This should be error resultant from pure noise of the measurement equipment/process set up uncertainty. The replicates should be spread throughout the testing cycle. The SS lack of fit error is the SS of the means of the replicates about the fitted model. Here the F ratio computed is a measure of the ratio between the lack of fit and pure error SS. We want this F ratio to be 1, as that would imply that the only contribution to the error is from pure noise error and not from model innacurracy.
![[multivar_ANOVA_SS_error.png]] 
![[multivar_ANOVA_SS_error_fit.png]]



#### Limitations of ANOVA
