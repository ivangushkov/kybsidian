## ML Estimation
[[Least squares]] is purely geometrical, ML is an extension that allows us to utilize assumptions about the [[Statistic]]cal distribution of the measurement noise!

	Injecting assumptions yields better performance when they are good, 
    but WORSE when they are bad

### ML vs LS
LS means "state the fitting problem as just a geometrical one"
ML means "add the assumption that there is an underlying probability distribution"

In both cases, we can find solutions using numerical optimization on some cost function on y and theta

#### Geometrical intuitions
We are now considering the [[Likelihood function]]. The interpretation of the "best theta" i.e. the maximum likelihood estimate, is the value of theta which maximizes the likelihood of y.

Put in another way: A fixed measurement of y will collapse the bivariate function to a function whose value only varies in theta. The function value for a given theta is a representation of how likely a distribution with that theta is to produce y. Thus, the theta that maximizes this new function (likelihood function) is our estimate.
![[multivar_likelihood_cut.png]]

Note that the shape of the likelihood function depends on our assumption of the PDF. If our assumption is wrong, the peak of the likelihood function will not align with the "true" peak of the likelihood, thus yielding a bad estimate.


#### Mathematical Formulation

After we have defined some likelihood function and obtained a dataset D, we can formulate the ML estimator as follows.

$\hat \theta_{ML}=argmax_{\theta \in \Theta}p(D;\theta)$



#### Useful trick:
If we have a monotinic transformation applied to the likelihood function, the argmax of the original will be the argmax of the transformed. We usually use log since it squashes exponentials. Further, maximizing is equal to minimizing the negative function.

$\hat \theta_{ML}=argmax_{\theta \in \Theta}p(D;\theta) = argmax_{\theta \in \Theta}log p(D;\theta) = argmin_{\theta \in \Theta}-log p(D;\theta)$ 

Here we are injecting assumptions, but some of the consideration that we had with LS also apply. For example, we can still get the problem of the solution falling outside the valid hypothesis space.

**Some properties**

- If the likelihood is continious on a compact hypothesis space there exists a solution (Vaestraz's theorem). 
$p(y;\theta) \in C^0(\Theta)$
$\Theta$ compact
	$\Rightarrow$   $\exists \hat \theta_{ML}$ 

- Otherwise a solution might still exist if $\Theta$ is not compact, so long as the maximum is not on the border (continious + bouded is sufficient but not necessary).

- Uniqueness of Solution - the likelihood function might have multiple equal global maxima, meaning we might have more than one solution for the ML estimator.
- Assuming the Gaussian case the ML collapses into the LS solution.
- The derivative/gradient equal to zero at the ML solution is not a necessary condition. We might have the case that the derivative is not defined at the minimum, or the minimum is at the border of the hypothesis space with the function still decreasing.
- List of sufficient (not necessary) conditions for the ML estimate
	
	1) The derivative and second derivative of the likelihood exist in the interior of the hypothesis sapce:
		$\nabla l, \nabla^2 l \exists$ in int $\Theta$ 
	2) The gradient at the estimate is zero (assures it is a local extremum):
		$\nabla l(\bar \theta) = 0$     
	3) The second derivative at the estimate is positive (assures the extremum is a minima, since if curvature is positive the function grows all around):
		$\nabla^2 l(\bar \theta) > 0$ 
	4) The likelihood is convex (assures that the local extremum will be the global one):
	5) The hypothesis space $\Theta$ is convex
	6) Estimate on the interior of hypothesis space $\bar \theta \in int \Theta$ 