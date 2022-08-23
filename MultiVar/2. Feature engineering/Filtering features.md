Baseline approach to [[Feature selection]], by removing all features that have low variance (i.e. little information).

Bit of a naive approach, but should be the baseline

Hyperparameter: How many features to remove?

Default value is zero, i.e. always remove all zero variance features (constants)




Intuition: Keep variables that have a statistically significant relationship from the input to the output.


May also use [[Correlation]] between input feature and output in the linear case. This approach is the "univariate approach", and considers any statistic between input feature and output



+Tends to be robust against overfitting
+Computationally efficient
+Independent of assumptions made in the learning algorithms (f.ex in [[ICA]] we require independent components)

-Tends to select redundant variables
-Requires choice of thresholds
-Do not consider interactions among features
-Do not consider the model being employed