

## TLDR
Usually the best performing objects with lots of positive properties
Random Forests are benchmarks, should always be tested!

Create a large number of individual [[Decision trees]] that operate in ensemble: Each individual tree makes it own prediction and the class with the most total votes becomes the final prediction

	We need relatively uncorrelated trees!


100% train accuracy does not necessarily mean overfitting! The Random forest is only overfitting if the [[Decision trees]] are very deep!

## Concept
Take the original dataset, X, Y

Sample with replacement n training examples from the dataset to create N datasets

	This sampling is done to induce relatively uncorrelated trees. This 
    is called "Bagging"
    
We may also randomize what features we use (Feature randomness) (No replacement since this may (?) lead to correlated DTs)


For each of the N datasets, train [[Decision trees]] fk_hat. The ensemble of these trees will be the final estimator, f.ex the average of all fk_hats

This ties back to [[Bias variance tradeoff]] where we reduce overfitting by making many datasets and taking the average of all the variations of individual trees


## Summary
* Works with both categorical and cont. variables
* Can handle missing values
* No scaling / normalization required
* **The voting gives an indication about uncertainty**
* High non-linearity between independent variables (data), RF may outperform other methods like [[SVM]]*
* Usually robust to outliers
* Very stable, since new data only impacts a subset of trees, not all
* Comparatively less impacted by noise


\*Example: A zone that RF may create that is HARD for others
![[Pasted image 20220721021259.png]]


