## Partial Least Squares Regression
This is a latent variables regression which maximizes the covariance between X and Y. The ideal case would look something like the figure bellow. PCR still has the problem of not taking care between correlations in the outputs, and moreover correlations between inputs and outputs. The components used for PCR are based on correlation structures in the X matrix, but nothing says they will be relevant for predicting Y. PLSR solves that, and also identifies structures in X which relate to the outputs.

![[multivar_plsr_ideal_case.png]]

#### Mathematical Formulation
Mathematically we start by calculating a covariance matrix between X and Y 
