

	No method that automatically determines this will work for all 
    various datasets


For [[PCA]], there are multiple definitions of rank:


1. Numerical rank - for all real data, it is the smallest dimension of the data table
2. Statistical rank - based on some statistical criterion
3. Application specific rank - based on experience and interpretation

Most systems are observed with more sensors/vars than the "actual" rank

Methods based on [[Latent variables]] will summarize information in "super variables", i.e. [[Scores]] and reveal each super vars contributuion [[Loadings]]!



Some approaches:


#### Cross validation
See [[Cross validation]]


#### Ratio of eigenvalues


#### Keep all eigenvalues g.e. 1


#### Let sum of PCs explain more than 95% of variance
		Not recommended


#### SCREE plot
A plot of eigenvalues vs # PC
![[Pasted image 20220714000236.png]]




### AIC and BIC