## Intuition
Strategy: Try to search several subsets of features, then evaluate the data modelling accuracy through [[Performance indices]] for each of these combinations.

Take the subset with the best performance


+Unlike [[Filtering features]], we can take into account possible interactions between variables
+Often finds a good subset for a specific learning algorithm

-Risks overfitting when the number of samples is low (increased chance of being lucky with samples) ([[Bias variance tradeoff]])
-Computationally demanding when the number of features is large

## Methods
1. Forward selection
	Start with having no features in the model
	Iteratively add features which best improves the model
	Stop when no improvement is observed

2. Backwards elimination
	Start with all features
	Prune the least significant features iteratively
	Stop when no loss in performance

3. Stepwise selection
    Reconsider all dropped or added variables 

4. Randomized werapper methods
	Include some randomness in selection


		3 and 4 are cursed by Damiano himself



## Notes
Wrapper methods tend to perform well on orthogonal designs, but not so well for correlated features.

This is because we may lose causality when doing [[Feature selection]]
