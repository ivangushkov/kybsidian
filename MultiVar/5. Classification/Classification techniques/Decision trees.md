## Decision tree




Split the feature space based on binary "greater than" questions.

	Ask linear questions until the data is fully classified

Each cut reduces the [[Impurity]] in the children, which is equivalent to maximizing information (minimizing impurity)


We split the data such that the different pieces are as different from one another as possible (equivalent to minimizing the difference inside each piece)

+Very interpretable!
+Requires very little data preprocessing
+The cost of training is log(number of data)
+Enables automatic feature selection
	The order of questions determines the most important features!



-Extremely prone to overfitting: A small variation in the data may produce a wildly different tree ([[Bias variance tradeoff]])
-Training performance is always 100%
-Very biased if some classes dominate (high bias AND high variance leads to high MSE!)



Decision trees are an alternative view of [[Logistic regression]]

![[Pasted image 20220721014655.png]]