## MAP Estimation


#### Basic Assumptions
- Already modelling the problem with probability/statistics theory in ML estimation, now we are injecting one more assumption. We will assume that we have some prior knowledge on the parameter $\theta$ and that can help us improve the properties of the estimate.
- We are now also modelling the distribution of the parameter $p(\theta)$. This will give good results if the prior on $\theta$ is good, but again we are complicating the situation with more assumptions.

#### Mathematical Formulation

We will be using [[bayes rule]] to update our probabilities and in fact now we will have a full pdf for the parameter $\theta$.

$P(A|B) = \frac{P(B|A)\cdot P(A)}{P(B)}$ 

A = $\theta$ , thus P(A) is prior on the parameter
B = y , thus P(B) is called evidence and acts as a scaling constant to make the product above a full pdf. Often omitted in computation
$P(B|A)$ = $P(y|\theta)$ = likelihood, same guy from ML estimation

$P(\theta | y) = \frac{P(y|\theta)\cdot P(\theta)}{P(y)}$

The object above is the posterior distribution and we are going to pick the theta which is its mode. Since P(y) does not change the shape of the curve, only scales it so that the area under curve is 1, we can omit it from the calculations:

$\hat \theta_{MAP} = argmax \theta \in \Theta P(y|\theta) \cdot P(\theta)$

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