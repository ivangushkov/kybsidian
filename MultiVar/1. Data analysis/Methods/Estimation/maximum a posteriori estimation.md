## MAP Estimation


#### Basic Assumptions
- Already modelling the problem with probability/statistics theory in ML estimation, now we are injecting one more assumption. We will assume that we have some prior knowledge on the parameter $\theta$ and that can help us improve the properties of the estimate.
- We are now also modelling the distribution of the parameter $p(\theta)$. This will give good results if the prior on $\theta$ is good, but again we are complicating the situation with more assumptions.

#### Mathematical Formulation

We will be using [[bayes rule]] to update our probabilities and in fact now we will have a full pdf for the parameter $\theta$.

$P(A|B) = \frac{P(B|A)\cdot P(A)}{P(B)}$ 

A = $\theta$ , thus P(A) is our **prior** on theta.
B = y , thus P(B) is called evidence and acts as a scaling constant to make the product above a full pdf. Often omitted in computation. Thus, we have

$P(\theta | y) = \frac{P(y|\theta)\cdot P(\theta)}{P(y)}$

Note that $P(B|A)$ = $P(y|\theta)$ is the [[Likelihood function]], same guy from [[maximum likelihood estimation]] estimation. In a sense, the MAP is the ML estimate, injected with prior knowledge about the distribution of the theta. That is, we don't directly trust the maximum likelihood because we hold some prior knowledge on theta. However, we would still like to consider both the prior and the maximum likelihood from a new measurement, and so we multiply them together to update our belief.

	If our prior information is good, we can improve on ML by 
    considering what we know with new information. However, if our prior 
    is bad, MAP will also be bad.


$P(\theta | y)$ is the posterior distribution, and the MAP estimate will be the theta that maximizes the posterior (the mode of the posterior)
![[Pasted image 20220710154107.png]]
Since P(y) is a constant, it does not affect the argmax, and so we can omit it from the calculations

#### Geometrical Intuition
The figure illustrates a problem with MAP discussed in the next section.

![[multivar_map.png]]

#### How to compute the MAP practically

4 main methods

- Analytically - if mode of posterior can be obtained in closed form. Preferable to anything else, as is cheap and efficient and also most accurate, but in general not trivial.
- Numerical optimization - scipy to the help. Keep in mind that we will have to compute first and second derivatives, which may be its own analytical/numerical problem to solve.
- Via modified expectation-maximization algorithms. This does not need derivatives, but is more advanced.
- Via Monte Carlo sampling based methods when all else fails. Particle filters and stuff. This is the nuclear bomb.

Caveat with MAP: it will pick the mode of the distribution. The mode might not be the best representation of the sample space. Consider again the figure in geometrical interpretations and see that the area under the mode is a lot less than the one under the second peak. That is, there is a higher probability that the parameter will be in a neighborhood around the second peak than around the mode.