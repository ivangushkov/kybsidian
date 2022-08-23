## Gradient descent
If we cannot find the [[Least squares]] solution analytically, we can use Grad. descent.

Next theta = current theta - alpha * grad * cost(theta)

Gradient yields ascent, so minus gives descent

### Flavors
Batch gradient descent: Calculate each theta at a time using the full gradient
Stochastic gradient descent: Only find the gradient for one sample at a time, instead of the whole cost function!


Stochastic tend to outperform Batch!