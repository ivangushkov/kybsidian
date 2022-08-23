# Prediction Error Methods
This is one paradigm where we are looking for the yhat that is closest to y


## Ingredients
![[Pasted image 20220718175856.png]]

* Not all errors may be desirable to be treated in the same way. Ex. a collision is much more important to minimize than f.e.x fuel efficiency for a car


* A common choice for the loss function is the standard 2norm. It may also be desirable to replace this with [[Huber loss]] to avoid square losses out far affecting the model to much.

* The loss is averaged in time!


		We tune y_hat, theta is a consequence of this!

Since y is a function of u, we are looking for a yhat that can predict y given u


## Approach

1. Decide which model structures you want to test, like [[ARX]], [[ARMAX]], [[OE model]] etc... and their associated orders
2. For each model find the predictor y_hat in theta
3. For each model find the best theta through a cost function as a function of y_hat
4. Decide which model and order is best through [[Model Validation]]

The more complex the predictor is the higher variance ([[Bias variance tradeoff]]), which reflects in more local minima in the cost function in 3.


## Ideal case
The model order is correct and we know both G and H, then the prediction error should be white iid!

That is, white noise holds no information, and such if the error is white, we have used all our information to make the prediction!