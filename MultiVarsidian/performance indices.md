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
Note that all statistical performance indices compress model error into a single number, and thus they all highlight different aspects of error characteristics. Different PIs perform more or less conservatively as a function of error dataset characteristics like variance and mean error magnitude.

**RMSE** - Fisherian approach $\theta$ is unknown but deterministic, so we do not have a full posterior distribution, therefore no MAP. As mentioned earlier, MSE is an expectation of how far we land from the parameter. This is a measure on the distribution of the dataset, which is a function of the true parameter. Since we do not know the true parameter, we cannot compute the MSE and the RMSE. We have to estimate/simulate it. 

Usually we will have to do something like this:

$\sqrt{\frac{1}{N} \sum_{t=1}^{N} (y_t - \hat y_t)^2}$   **NOT PARAMETER MSE, THIS IS AN ALTERNATIVE PROXY FOR IT**

**RSS** - Residual sum of squares. Problem with this PIs is that when minimized, it will fit better to areas of the data with bigger magnitude, and moreover will fit differently depending on the size of the dataset (bigger the more stuff you sum up). There is a need for normalization, which leads to the FVU.

 $RSS = \sum_{t=1}^{N} (y_t - \hat y_t)^2$

**FVU** - Fraction of Variance Unexplained. This is RSS normalized by the length and the variance of the dataset. This is independent of scale and size of dataset. Will map between 0 and infinity. 0 means there is no variance in the dataset which is unexplained. Will map to 1 if we just average the data. More than 1 means we are doing worse than average/trivial estimator.

$FVU = \frac{RSS}{N\cdot var(y)}$

**R2** - Coefficient of Determination. Proportion of the variance in the dependent variable that is predictable from the independent variables. This is a sort of correlation based measure. The problem with correlation coefficients is that they are inherently only a linear measure. Samples distributed according to a say parabolic model might have low correlation.

$R^2 = 1 - FVU = 1 - \frac{RSS}{N\cdot var(y)}$ 



**MAD** - Mean Absolute Deviation.
Defined as the expectation of the absolute value of the error

$MAD = \mathbb E [|{y-\hat y}|]$  

Say we have some sample on the errors we can calculate the sample MAD as follows.

$MAD = \frac{1}{N} \sum_n |{y_n-\hat y_n}|$  


**MAD vs RMSE** - what to use?

There is not a one clear answer. MAD will weigh all errors equaly. RMSE will penalize variance as it weighs errors with larger absolute value more. RMSE will grow as the distribution of error magnitudes becomes more variable. The RMSE will also grow disproportianetaly with dataset size. The RMSE is sensitive to outliers, especially for small set sizes. The RMSE is also sensitive to model/error biases (the case when error is not zero mean). On the positive side: RMSE is more well analytically posed. The RMSE is easy to differentiate and analyze for sensitivity. Also the RMSE is more sensitive to large systematic errors and thus better/more sensitive at evaluating between model performance differences. The RMSE highligts the big differences. On the other hand the RMSE will perform worse in the presence of outliers and non-gaussianity. A combination of error metrics is required to trully asses model performance!

When the error distribution is Gaussian and there are enough samples to represent the distribution faithfully, RMSE is better. The MAE (same as MAD) is better at describing uniformly distributed errors. The RMSE is related to the L2 norm, while the MAE is related to the L1 norm or the error vectors.


### Classification PIs
Chosing the right PI for classification is critical. The name of the game in choice of classification PI is making the following 2 considerations:

1) Balancedness of the dataaset - is my dataset dominated by one class or is there roughly equal distribution? What is the prevelence in a detection problem (how ofter does the "true" condition occur in the dataset, a measure of balancedness).
2) Importance of type 1 error versus type 2 error - are we detecting cancer? In such case the false negative (type 2) error is devastating and we should build classifiers who avoid it. Are we detecting objects in a computer vision based avoidance system? Then false positives might be critical (but also false negatives, but maybe less so).

![[multivar_classification_errors_figure.png]]


#### Meet the PIs
**Accuracy** - the dual of error rate. How often do we guess correctly, dataset be damned. Sensitive to dataset imbalance.

$Accuracy = \frac{true positives + true negatives}{N}$

**Precision** - When predicing "yes", how often are we correct? A PI which is good if false positives are an issue.

**Sensitivity/True positive rate** - Considering only the true appearances, how often does it predict true? Not sensitive to dataset imbalance.

**Specificity/True negative rate** - Considering only the negative occurances, how often does it predict negative. Not sensitive to dataset imbalance.

**False positive rate** - When it's actually no, how often does it predict yes?

**F1 - score** - aggregate of precision and specificity. Symetric to type 1 and 2 errors (if type 1 is important use precision)

$F1 = 2 \cdot \frac{precision \cdot specificity}{precision + specificity}$
