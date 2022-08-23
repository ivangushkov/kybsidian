## Splitting of Datasets

#### Problem Motivation and Assumptions
Split dataset in training, testing and validation to do parameter estimation, model selection and estimate performance in the real world respectively.

	The sets should be independent of eachother

If they are not, the bias of the model will increase, and the PIs on the withheld data will be worse.

	The sets should follow a similar probability distribution

If not, the testing and validation will be meaningless, since the training will be related to "a different reality".

#### How to do this in practice
Choosing the correct split is subtle and important. Note also that often, the "test" set is both test and validation, and that literature mixes test and validation.


	The lesser the dataset, the higher ratio of training / test, since 
    we require a certain amount of data to train a model with lower 
    variance

The results will vary drastically depending on how one splits. 

The third set is "witheld data". This is data that the estimator will not see before we have a structure and a set of parameters and want to estimate how they perform in the real world. 

**Splitting according to application:**
If the goal will be to forecast temporal signals we need to validate/test the model on a big chunk of unseen data.
This will ensure that the PI in real life is tested on extrapolation, which is what the model will do.
![[multivar_test_train_1.png]]


If the goal will instead be to produce some smooth processed results, i.e. interpolating between samples, (i.e upsampling of video), we may consider "every n-th sample".

![[multivar_test_train_2.png]]



**Splitting of temporal/dynamic data:**
When estimating in connection to dynamical systems and system identification, we have to consider that the training set needs to:

1. Cover all the operating areas in parameter space which the system is expected to work at
2. Not choose the same areas as for testing since then we will be overfitting our PI to similar operating ranges as the test
3. A temporal dynamic should as a whole be part of one set.

Consideration 1 ensures that many possible input-output relations are seen. This allows us to determine parameters and model order in a good manner.

Consideration 2 ensure that the test set provides meaningful information about model performance.

Consideration 3 ensures that the estimator is well behaved: If we do not include the entire dynamic, we could end up in a situation where we f.ex include the dynamics after an impulse without the impulse itself. From the estimator POV, this is "dynamics with a constant input", which would confuse the estimator.

Consideration 3 will be important for how the folds are chosen in [[Cross validation]]

![[multivar_train_test_dynamical.png]]



#### Properties of good set splits
In general also the test, train, validation sets should have the following properties:

1) Independent of each other (consideration b) in the paragraph on dynamical systems)
2) Follow similar probability distributions. This connects to the concepts of [[ergodicity]], [[heteroschedasticity]] and [[stationarity]]

 
