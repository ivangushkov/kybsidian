## Model Validation
Validating a model is mandatory. This is a rule and a mantra which is sacred and holds no matter what happens. There are many concepts and things to consider when one validates. There are two main purposes of validation:

1) Solving the [[Model Order Selection]] problem
2) Estimating the performance of the model in real life

There are many methods that are possible in regards to validation, however one thing holds regardless of method: one validates at the required level of conservativeness for the use of the model. A model which is required to predict and represent the underlying phenomenon at the most general level needs to be validated to the most general/conservative data stratification. Nevertheless it might be good to do validation on all levels and check how the stability evolves from low to high level of stratification. At the lowest levels we have individual data samples. At the highest levels we might have groups of samples comming from different farms, factories, countries etc. At the middle level we might get measurements from batches or days.

**The independent test set** - the independent test set is the best thing to do, almost always (we might have too few sample groupings at the highest level of stratification, see three farms). This should be picked at the highest level of stratification if such conservatism is required. Otherwise it should be picked (like everything else here) according to application and model utility. For predictive models the independent test set should be picked as extrapolation, as this is the thing we want to achieve.

**CV on the training set** - this is the best strategy hands down (excluding cross model validation). Here we also validate at the highest stratification level. No random splitting unless it makes sense.

**Cross Model Validation** - this is an improvement on the CV. This is essentially a 2 level CV, where a subset of the data is kept out in an outer loop, and the remaining is Cross Validated in an inner loop. The outer loop loops untill all the data has been part of the outer loop. This is quite conservative and it might detect lack of model where CV would not have. Especially in the underdetermined case, CV can lead to overfitting. If we have few samples we might get random and spurrious [[Correlation]]s along noise dimensions. The inner CV loop might validate at another stratification also in case we want to test stability at 2 levels at the same time.



## Practicalities

1. Check if estimated parameters are feasible
2. Check if the variances of these estimates are meaningful
3. Check if different estimation methods provide similar results
	If not, it may be a sign of undermodelling!
4. Check if applying model reduction leads to same results
	I.e. if we do [[MLR]] on a dataset and a [[PCA]] reduced model and they provide similar results, it is an indication of overmodelling
5. Check if simulations yield "reasonable" or "acceptable" performance.



# Example
Bad validation:
SBMPC: If the validation set is every n sample, we validate the MPC for **interpolation** of the ship paths. However, the domain we operate in, we need to know something about the **exterpolating** power of the model!!!!