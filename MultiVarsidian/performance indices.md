## Statistical PIs

![[multivar_exam_2022_l21.11.png]]
![[multivar_exam_2022_l21.12.png]]

Regression
- Categorize them into interpretable (FIT) vs not interpretable (RSS)
- Categorize into things based on squares and things based on absolute values (MAD).
- Compare use of absolute deviation PIs to squares based PIs and how abs div is more robust
- Make a table
- MSE is the tits, but we do not know theta apart from simulations


Classification
- Stress the type 2 vs type 1 error: cost of those errors
- Stress the balancedness of the dataset problem: PIs good for balanced vs unbalanced sets.

Purpose of PIs is to evaluate performance of estimator. Understand, interpret, chose PI based on the need of the problem.

### Regression PIs

##### Geometrical Examples
Picking what to optimize for will have drastic effects on the resultant estimate. If we optimize for error we might end up with the sine curve. If we optimize for variance (curvature of the estimator) we might end up with the smoother curve.

![[multivar_PIs_curves.png]]

The estimator will map a realization of the dataset to parameters. Different estimators will map the same dataset to different parameters. Moreover, data generated from the same real parameter will be a random variable, therefore the estimator will be a random variable. Meaning it will have statistical properties. The MSE for example is the average/expected distance in hypothesis space that we land away from the true parameter. So, the true parameter will induce a probability distribution on the data, the data distribution will be pransformed back into hypothesis space through an estimator and the RV properties with it.

FIGURE

#### The different indices
**RMSE** - Fisherian approach $\theta$ is unknown but deterministic, so we do not have a full posterior distribution, therefore no MAP. As mentioned earlier, MSE is an expectation of how far we land from the parameter. This is a measure on the distribution of the dataset, which is a function of the true parameter. Since we do not know the true parameter, we cannot compute the MSE and the RMSE. We have to estimate/simulate it. 

Usually we will have to do something like this:

$\frac{1}{N} \sum_{t=1}^{N} (y_t - \hat y_t)^2$   **NOT MSE, THIS IS AN ALTERNATIVE PROXY FOR IT**

**RSS** - Residual sum of squares. Problem with this PIs is that when minimized, it will fit better to areas of the data with bigger magnitude, and moreover will fit differently depending on the size of the dataset (bigger the more stuff you sum up). There is a need for normalization, which leads to the FVU.

 $RSS = \sum_{t=1}^{N} (y_t - \hat y_t)^2$

**FVU** - Fraction of Variance Unexplained. This is RSS normalized by the length and the variance of the dataset. This is independent of scale and size of dataset. Will map between 0 and infinity. 0 means there is no variance in the dataset which is unexplained. Will map to 1 if we just average the data. More than 1 means we are doing worse than average/trivial estimator.

$FVU = \frac{RSS}{N\cdot var(y)}$

**R2** - Coefficient of Determination. Proportion of the variance in the dependent variable that is predictable from the independent variables. This is a sort of correlation based measure.

$R^2 = 1 - FVU = 1 - \frac{RSS}{N\cdot var(y)}$ 



**MAD** - Mean Absolute Deviation.

