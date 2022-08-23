## Over and Underfitting

#### Underfitting
A model that misses fundamental/important features of the data. On a macro scale it follows a trend, but is too simple to explain the variation in the data. The model output will not be affected much by the data inputs, thus yielding low variance but high bias - the [[Bias variance tradeoff]]

	Performs bad on training and bad on test

#### Overfitting
A model that follows the data "too much" and has too many features. This leads to a very complex model.

	Performs well on training but bad on test

Since so many features affect the output of the model, small changes in the data will result in wildly different model outputs, despite the model performing extremely well (by some [[Performance indices]]) on the training data (from the [[Splitting of datasets]]). This translates to the model having very high variance (varying for small changes in data) but low bias - the [[Bias variance tradeoff]]



## Performance
#### RSS and MSE
Training: Increasing performance with increasing model complexity forever
Test: Increasing performance with increasing model complexity up to a certain point, at which it will get worse again.



## Practical approach
Make many models and run the first two stages on all of them. Then find the appropriate complexity that avoids both over and underfitting