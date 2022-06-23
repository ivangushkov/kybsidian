# PCA

![[multivar_exam_2022_l2114.png]]

Principle Componend Analysis, or PCA is a method for [[dimensionality reduction]] of datasets. It finds special directions called Principle Components, and expresses the data in an [[orthogonal]] coordinate system given by the principle components. The directions of the principle components have importnat mathematical and geometric intuitions, and are meaningful for the dataset.

### Geometrcial Intuitions
PCA finds the directions called principle components. The first principle component is a [[least squares]] fit line of the data. This is because the PC1 direction is the one along which [[variance]] of the dataset is maximized, which also happens to be the same direction where the square of orthogonal residuals is minimized (dual formulation of the same thing). The second PC will lie along the direction of second largest variance, while being constrained to orthogonality with the first PC and so on. Since the PCs are connected to [[least squares]], outliers will heavily skew the result, as LS is a purely geometric method of fitting to data. This is the concept of leverage and wil be important in outlier detection. PCA also finds these directions "bottom-up" so that it starts with the first PC and finds PC2 and so on. This means that the higher PCs don't have a bearing on the lower ones, and as such a truncation can be performed on the order of the PCA. This is the mechanism behind the dimensionality reduction of the PCA.

![[multivar_pca_geometrical_intuition.png]]



### Mathematical Formulation
PCA is intimately connected to the [[SVD]]. In fact it can be said that the SVD is the purest mathematical expression for the PCA. Recall that the [[SVD]] is a unique decomposition that exists for every matrix, factorizing the matrix into 3 matrices U, $\Sigma$ , $P^T$ . The columns of U are called left singular vectors, the columnts of P are called right singular vectors and the values along the diagonal matrix $\Sigma$ are called the singular values. These are stacked from right to left in order of increasing importance for explaining the variance in the dataset. In fact, a truncation of the first r singular values/vectors represents a truncation to the first r PCs. From a truncated set of singular values and vectors, an approximation of the original matrix can be reconstructed, and in fact the Eckart-Young theorem tells us that the SVD will provide the optimal truncated approximation of the matrix for an order r in terms of the Frobenius [[Norm]].

(E)SVD notation:  $X_{m x n} = U_{mxn} \Sigma_{nxn} P^T_{nxn}$
Truncated SVD: $X_{m x n} = U_{mxr} \Sigma_{rxr} P^T_{rxn}$

PC system = new coordinate system made up of the data variables combined in a linear fassion. That is, each PC is a linear combination of original data features.

Loadings = P^T matrix. Loadings are the relations between original/variable space axes and PCs. Each PC is a combination of original variable basis vectors and the loadings give the scalings for the axes. Loadings provide the "recepie" for a PC starting from original variables.

Scores = T matrix. The coordinates of the data in PC space, and will thus represent how much along each PC to combine to make a data point.

### How to practically do PCA
##### Interpreting Scores Plots
The score of a sample along a PC will tell us something about that sample in terms of the latent variable modelled by the PC. Say PC1 somehow represents North-South and PC2 represents coast-inland relationships between cities. A sample with a low score on PC2 while having a very small score on PC1 will be a close to coast city halfway down across Europe (maybe Dublin). Notice however that a deep interpretation of the scores plot is contingient on having a good interpretation of what the latent variables modeled by the PCs represent.

###### Interpreting Loadings Plots
- Loadings and Correlations - Variables close to each other in the loadings plot will be correlated if these specific variables explain a large portion of the variance of the data for these variables. Consider that maybe some variables are close to each other for PC6 and PC7 loadings plot, but PC6 and 7 only explain 2-3% of the variance. Maybe in the first components where a lot of the variance of these variables is explained they are not close to each other, then they are probably not correlated. With the same logic variables oposite to each other may be negatively correlated if the explained variance is high.
- Correlation Loadings plots - the absolute value of the numbers along a loadings plot axis itself will tell us very little, as they are also a function of the explained variance for the dataset. Recall that the loadings are orthonormal, meaning the loadings vectors have to have length 1. A dataset with hundreds or thousands of components will have very small numbers along the loadings axes even for the first principle components, unless those components utterly dominate the variance of the dataset. Thus, to better interpret the numbers we can plot the so called correlation loadings. Consider that for a single feature, the sum of the variance explained by each principle component for all principle components should sum to 1 (the combination of all PCs ultimately explain an original variable). The correlation loadings are the square root of explained variance for the specific PCs plotted. Consider the figures under. The two circles represent that 100% and 50% explained variance for the variable. So Ti and Ca have something like 90% explained by the first two principle components, while they do not at all explain Y. However, it can be seen that Y is explained to almost 100% by PC3 and PC4, even though those two PCs only explain 19% of the total variance in the dataset. The inner circle represents 50% explaine variance, and since a correlation is the square root of explained variance, we do not have a linear relationship (the 50% circle will not be halfway from the origin). Here is how to interpret coordinates in correlation loadings plots: say a variable Co (the element copium, used extensively by kyb students in the exam period) has correlation loading value of 0.5 along PC1 and 0.2 along PC2. Then PC1 explains $0.5^2 = 0.25 = 25\%$ of the variance in the original variable Co, while PC2 explains $0.2^2 = 0.04 = 4\%$ of the variance in the original variable Co. So together PC1 and PC2 explain 29% of the variation in the Co variable.

![[multivar_pca_correlation_loadings_01.png]] 
![[multivar_pca_correlation_loadings_02.png]]


###### Validation
For PCA solving the model order selection problem means choosing a number of PCs, or truncation order for the SVD. There are multiple ways of doing this. The dumbest is just going ooga booga 95% explained variance good, but this will in general tend to overfit as a general dataset might get to 95% explaied variance long after any structure has stopped happening. Another strategy is the "elbow strategy", seeing where a large slowdown in the explained variance plot stops happening. This will again not work for the general dataset. For data scaled to unit variance choosing the order at which the eigenvalue gets under 1 might be a good idea. We might also pick the order where we get close to 1 for the ratio of eigenvalues. At any rate and always we do cross validation. Cross Validation for PCA happens when we take out a subset of samples, make a model with the rest, project the witheld data into PC space, then estimate the witheld data from the projection and evaluate the variance of the error (the variance we don't explain). If a model truly is there, there should not be much instability to taking out some samples. Grouping for the CV folds should be done after sample groupings for most conservative Cross Validation. For example, grouping after year will validate if the model is stable temporally, that is is there a real model which can predict across years. This is the 112233 scheme. A scheme like 123123 rather tests if the model is stable for repeated experiments. Why is cross validation important? Well, even for random data with small enough number of samples we might get what looks like systematic variation in some directions. PC1 or 2 might explain 30 or 20 %, but this will quickly collapse under Cross Validation. A Cross Validated explained variance plot is always more valuable than a non cross validated one. Under validation with no model the scores will tend to move towards the center, indicating that the best model is just averaging.


###### Outliers Detection
For outlier detection we need two concepts. Leverage is the distance of a sample from the mean along the hyperplane of the model. It is essentially how important a sample is to the model. Residual is the distance of a sample from the hyperplane of the model (assuming we have determined some model order). Samples with high leverage will be influential for the model. Samples with high residual are not well described by the model. Samples with both high residual and leverage might be true residuals and we can consider removing them, however handling outliers in general is not black and white. Samples with high residuals might simply not follow the pattern for some features. If there are few of these samples, and we have a stable model (cross-validated, because we GIGACHADS) we can actually imputate the part of the datavector which is not according to the pattern and predict it. Samples with high leverage might be important for the model and we cannot just take them out. Consider also that it matters if we have categories to the data. Maybe there was some systematic error in how the outlying data was collected, say if there truly IS a systematic variation in this higher dimension, but we have some unbalance in the gathering of the data which results in data from that region not being well represented. Mislabling, mishandling or sensor errors are also possible. Manual investigation might be waranted, use of domain knowledge recommended.
![[multivar_pca_residual_leverage.png]]

What is "high" can be determined by residual statistics. For leverage outliers we have the Hotteling's $T^2$ statistic, which is approximately F distributed, so we can get critical limits from that distribution. For leverage we have a linear relationship between that and Hotteling's, and the critical limit can be estimated from say 3 times the average leverage. Both are normalized for number of PCs and samples. We can plot stuff like estimates of confidence ellipses and whatnot based on these. However, again we should be careful. In the plot under it can be seen that the samples outside the ellipse are clearly a part of some structure. In the other plot we might be justified in removing samples, but again we can have the systematic data collection errors when it comes to categorical variables.

![[multivar_pca_outlier_ellipse.png]]

Error's residuals are from parts of the data which have not been modelled. This should idealy be iid, meaning no systematic variation should be found there. E of X and model can be estimated by approximating X through the model and finding the difference. This is also a function of truncation order. Q residuals is the squared sum of X residuals for each sample. A critical value for the Q residuals from formula. F residuals are the square root of Q residuals divided by the number of variables. F and Q residuals are a statistic of residuals. When plotted against the Hotteling's $T^2$ we get the Influence plot, which can be used for outlier detection.

![[multivar_pca_outliers_influence_plot.png]]


#### Limitations of PCA


#### Example - Europe City Temperatures

The features are a function of time (the months of the year) and we have a dataset which varies in that 12-D space. Hidden in the variation is the North-South, coast-inland relationships. 

Loadings plot for this dataset: 
In the loadings plot the winter months had higher values for PC1, meaning they explain better temperature variation (there is more systematic temperature variance in the winter months). PC2 represents 