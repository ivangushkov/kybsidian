## ML Estimation

#### Motivation and Basic Assumptions
- Recall that LS and all its flavours are purely geometric. We wish to extend our estimator to also include information about the statistical distribution of the noise.
- Watch out that we are injecting assumptions about the way the world works. If we assume a good structure and our model for the noise is good then ML will outperform LS. Otherwise we might get worse results.


#### Geometrical intuitions
We are now considering the likelihood function. When an assumption is made for the statistical distribution of the measurements, we will obtain a pdf for the data. This pdf depends on both the data and the parameter and can be seen and plottet as a bi-variate function in the data and parameter. Consider the Gaussian case where the parameter $\theta$ is the mean:

$f(y_t;\theta) = \frac{1}{2\pi\sigma^2}exp(-\frac{1}{2\sigma^2}(y_t - \theta)^2)$   

Notice how we can either keep the parameter fixed and obtain a cut which would be the pdf for the data, or we can say that we have obtained a realization of the data, keep that fixed and obtain a cut which will be the likelihood for the parameter. The difference is that the case of a fixed $\theta$ models a probability of a measurement (something that has to happen in the world) meaning the pdf has to integrate to 1, while the case of a fixed data models something which has occured and the likelihood does not have the same constraint of having to integrate to 1. The interpretation here is that a parameter which maximizes this likelihood is considered good, since it is most likely given the observed data than any other parameter.

![[multivar_likelihood_pdf_bivariate.png]]

![[multivar_pdf_cut.png]]

![[multivar_likelihood_cut.png]]

#### Mathematical Formulation

After we have defined some likelihood function and obtained a dataset D, we can formulate the ML estimator as follows.

$\hat \theta_{ML}=argmax_{\theta \in \Theta}p(D;\theta)$

If we can define a monotonic transformation of the likelihood, the parameter solution which maximizes the transformed function will be the same as the one which maximizes the likelihood. Often used transformation is the log. Then maximizing the log likelihood is the same as minimizing the -log likelihood.

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