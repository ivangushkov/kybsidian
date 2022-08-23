How to select a subset of relevant features for use in model construction.


	If the data is bad, the results will be bad. Well behaved data tends 
    to yield similar results for all the methods presented here

## Why?
By selecting a subset we are promoting parsimonity and reducing variance from the [[Bias variance tradeoff]]!

	Feature selection may help avoid overfitting.

We can also achieve shorter training times and less computational loads

Interpretation may be easier

Avoiding the curse of dimensionality

Note: Feature selection problem blends with the [[Estimator]] design problem, in the sense that figuring out what variables are important is very similar to estimating effects etc..

	Note: We need to define which performance indices to be maximized 
    before going ahead with the objectives

	Note: We need to decide how many trials to perform (the more trial 
    the more the risk of overfitting (hitting a lucky sample etc))

	A "trial" is a model based on a certain subset of the data/variables

## Objectives
Remove "useless" variables while adding features that yield better performance.

Note that we can introduce new features from the original data by any transformation such as sqrt, exponentiating etc...

## Notes
* Many methods will give similar prediction errors with proper [[Model Validation]]
* Different methods with the same objective function should give similar results
* Often better to judt remove the non-significant variables than checking all the combinations of N variables and picking up one of these combinations
* If the datasets has few samples but many variables, then any variable selection method will be bad.


Methods like [[PLSR]] do not need feature selection, since this is handled implicitly

However, doing feature selection may be good since we can improve prediction ability and ease interpretation.

For machine learning, we very much need to do feature selection

Always aid findings with visualization!

## Common methods

[[Filtering features]]
[[Wrapper methods]]
[[Embedded methods]]
[[Decision trees]] and [[Random forest]]