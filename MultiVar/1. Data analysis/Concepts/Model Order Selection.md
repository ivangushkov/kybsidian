## Model Order Selection
Choosing the model order and structure. The model order selection is tightly coupled with the [[Bias variance tradeoff]] and we are making a tradeoff between [[Over and Underfitting]]


#### Definition
Selecting a statistical model from a set of candidates considering their statistical [[Performance indices]] on a given set of data.

Example: In [[PCA]], how many components should we choose?!

#### Ockham's razor
The simplest model that sufficiently explains the data is the best one

## Considerations
* Relevance
	* How significant is the model?
	* How interpretable is it?
* Parsimony
	* "Few parameters but satisfactory levels of fit"
	* How much do we actually want to have few parameters?

[[Cross validation]] is also a way to do model order selection.


## Simplest strategy
Estimate [[RMSE]] or MSE or other [[Performance indices]] from the data using many different models, and select the model with the amount of parameters that yields best tradeoff of training/validation error, then test on unseen data to judge performance.

Just looking at the training data alone means that we will likely overfit! I.e. the more parameters we have, the less the MSE, and the more we overfit! 


## Practical needs
If we have a stream of data, how do we do [[Splitting of datasets]]? If we are updating, we would want the new data to be all of the datasets..

We may actually use all data for training here, and decompose MSE differently...
This leads to the [[Stein Unbiased Risk Estimator]].

Additionally, the [[Information criteria]] methods can be used to perform this online!

## In practice
1. Typically, order selection is done by looking at data outside of the training
2. If it is not possible to do this, we may select order from the training set alone, but in this case we need to add some penalizaton terms ([[Information criteria]])
3. No magic approach that works everytime!
4. Always do model order selection :)






#### Model Order Selection in Practice
Simplest way of solving the model order selectio is the train/validation/test split. For all possible proposed models estimate parameters on the training set, estimate some statistical [[Performance indices]] on the validation set and pick the order with the best one.

**Relevance vs Parsimony** - The case is that the maths do not always give a clear cut answer. This is the "engineering" part of the course. We are engineering a model. This model has some use and will do something for us. It has some utility/relevance. At the same time Occam's Razzor holds, meaning we have to choose a simpler, more parsimonious model. Different people will interpret the model order selection differently. They might both be right from their point of view on the utility of the model.

**Recursive Estimation** - Doing the train/test/validation split will not be possible with recursive estimation. We want our newest data to be both training, test and validation. Here we have only training. In fact we can use a smart split of the MSE in order to derive a performance index which, when minimized, will result in a valid solution to the model order selection even when using only a training set. Enter the Stein Unbiased Risk Estimation framework. Consider the following PI:

$\hat R = -n\sigma^2 + ||y-\hat y ||_2^{2} + 2\sum_{i=1}^{n} cov(y_i, \hat y_i)$

The first term is purely connected to the noise. The second term is the empirical MSE proxy, the RSS. The last term is interesting. It is an (empirical) expression of the covariance between estimate and data sample. The covariance will be zero in samples which are not part of the training set, while some value for samples who are. Moreover this term will grow with model complexity, and balance out the diminishing RSS. This in practice means we can actually store this and keep updating it as samples arrive, making a model order selection decision. Pretty nifty!

**Information Criteria Methods** - Here we would like to minimize the difference of the estimated pdf to the hypothetical true pdf which produced the data. The Kullback-Leibler divergence is a measure representing the loss of information when a proposed model is used to represent the real pdf. This is in practice impossible to compute as it requires knowledge of the true pdf, but just as with the MSE there are proxies.

Two metrics here are the Aikake Information Criterion (AIC) and the Bayesian Information Criterion (BIC). AIC tends to pick more complex model, especially if there is a lot of data. BIC will be more persimonious but might perform worse in prediction. Choosing this is a trade off between performance and interpretability. Again we can have ambiguities. These methods can also be used to do model order selection on just training. We will have a term in there which penalizes model order, and we can optimize on two levels, recovering two solutions: the parameters and the model order.

**Tips on Cross-Validating PCA** - Do not split randomly unless that can be done safely. When doing CV always try to chose the folds from domain knowledge and be clear on what level you want to validate before seeing the data. Random CV might introduce variance in the estimate, especially for small datasets. Use the folds for sensitivity analysis, that is check if the performance varies greatly between the folds. This might be a) sign that there is not really a model but actually also b) sign that we have split the folds wrong. Further investigation at that point is waranted.

Damiano's Algorithm for splitting 50/50, apply with caution only if no natural groupings:

1) Compute distances among all samples
2) Take most distant pair and place in training
3) Take the next most distant, place in test
4) Take the sample most distant from the current training set and add it to the training set
5) Take the sample most distant from the current test set, and add it to the test set
6) Repeat 4 and 5

Might want to do 3 and 4 a few extra times a step in order to extract a validation set. This algorithm has the goal of making a training and test set which faithfully represent the span of the dataset. Both should be quite spread. Great for small datasets.

**Final Validation of the Model** - here we check if the model is good enough, meaning we have to define what is good enough for our application. Check if parameters make sense (feasible). Check if estimates eprical variance is meaningful. Check if different (simpler) estimators provide similar results. Not similar results here means probably undermodelling. Check if applying compression techinques and taking the same estimator in comressed data leads to same performance. If so we are maybe overmodelling. Check final performance in a simulation. Does the model do my job well enough?




