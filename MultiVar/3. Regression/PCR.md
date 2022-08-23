## Principle Component Regression
Replace the variables in [[MLR]] using the score vectors from [[PCA]]

We then use these to make a regression model in Y

This works since the [[PCA]] scores are orthogonal by design

We also avoid the no noise assumption by moving it to "no noise in score vectors", which is reasonable given that [[PCA]] separates noise from systematic variation.

	We can also use PCA and Tsq test to remove outliers


![[Pasted image 20220717213235.png]]

Where b hat is the LS / modified LS solution



## Problems
There is no guarantee that the PCs which explain optimally X, could be relevant for Y!
Alternative: [[PLSR]]





**Motivation** - PCR is the simplest latent variable modelling method. It tries to fix the problems of MLR. Recall that MLR is an orthogonal method, it will work best if the data matrix columns are orthogonal. This is not often the case, we have very often [[Correlation]]s in variables. This can cause ANOVA to have problems and declare no structure in highly correlated datasets. This reflects the fact that there is some lower dimensionality to the data.

#### Geometrical and Intuitions
Here we wish to exploit latent variables structures in the data matrix. Thus, we first run a PCA on the data matrix X, and then use the scores as inputs for an MLR fit. 

![[multivar_pcr_illustration.png]]


#### Advantages of PCR
PCR will have multiple results for us. 
1) We do not have to worry as much about what variables to include. We can just use the entire X matrix, and assume that choosing a good truncation will remove the effect of variables which are completely useless, thus no need to worry about regularization we just perform the a lot simpler process of validating and model order selection for the PCA. 
2) We have removed the assumption for a noiseless X, this is rather replaced by an assumption on noiseless scores matrix T. This is however fine, as it can be said that an oportunely truncated PCA will result in scores T which are mostly structure. Thus we have used the noise removing effects of PCA. 
3) We get all the tools PCA has for outlier detection.
4) Scores are orthogonal, thus MLR will work better. Also can independently interpret relation of each column of T to y.
5) Can handle missing data through [[MultiVar/1. Data analysis/Methods/NIPALS]]. Also only need to have more datapoints than truncation variables, wich is good for short fat matrices with many correlated columns.
6) No need to worry about selecting X variables. On the other hand we have to solve the [[Model Order Selection]] problem for PCA

