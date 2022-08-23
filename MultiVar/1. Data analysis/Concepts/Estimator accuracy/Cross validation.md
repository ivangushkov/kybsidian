Do independent repetitions of [[Splitting of datasets]]:

	Be clear about what you want to validate before doing this!

This is all non-withheld data. This is done for all model orders. By having an ensemble run for each model order, we achieve robustness.
![[Pasted image 20220710170141.png]]

For temporal dynamics, its important that the folds do not "cut" important parts, like cutting the dynamics after an impulse from the impulse itself. This is dependent on us having prior knowledge!

	Cross-validation is a resampling method


### Example with PCA
We can select the optimal # of PCA components with cross validation, as a [[Model Order Selection]]
1. Define a subset of samples to be kept out
2. Make a model on the remaining data
3. Project the samples kept out onto this model
4. Estimate the residual variance for these samples (distance between actual sample and reprojection)
5. Repeat until all samples have been kept out once


By checking the residual variance we can see how the model changes for varying training data. If there is large variation, this indicates too high variance , i.e. [[Bias variance tradeoff]]!!!

	Random data may have "good" cumulative variance, but will have 
    terrible explained variance when cross validating


	For random data, the best model will be the center, and so all 
    reprojections will move towards the center!



## Regression
When doing cross validation for regression models, we keep out both X and the Y reference



