A type of [[Feature selection]], where instead of optimizing the accuracy of the estimator, search for the set of features that optimize some objective function of a predictive model.

As we saw in [[Wrapper methods]], judging goodness based on the performance index directly may yield overfitting. ([[Bias variance tradeoff]]) Embedded methods try to eliminate this by instead optimizing an objective function

This requires defining a supervised learning model, which will then determine the importance of each feature for predicting the target features.

[[Regularization]] can be used for this! The cost function from [[Ridge regularization]] or [[Lasso regularization]] is then used for the optimization problem here.


+Feature selection and learning can be done simultaneously
+Less computationally expensive than [[Wrapper methods]]

-Feature selection performance cannot be separated from learning performance