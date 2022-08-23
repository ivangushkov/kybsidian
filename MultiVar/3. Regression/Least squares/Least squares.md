## LS

### Assumptions
Data is generated from a model $y = f(u; \theta) + v$
where f is the "underlying model" while v is noise. Each variable is for a given time instance f.ex

	Assume that the order (structure) of f is known, while theta is 
    unknown

The dataset is a collection of u's and y's

The hypothesis space is $\theta \in \Theta$

### Goal
Find a $\hat \theta$ such that $f(u; \hat \theta)$ is as close to y as possible. 

In other words, find the specific $\theta$ values which "best explains" d, i.e. best models the relationship between y and u.

### Geometric intuition
We aim to find a hyperplane of dimension equal to the amount of thetas in f. We vary the thetas and find the set of thetas that makes f "closest" to y, i.e. minimzes the distance between our data and the function.

One may also see this problem from the span of y: f spans a manifold embedded in the space the point y lives in, and theta moves along this manifold. The optimal theta is a point on this manifold that is closest to y.

### Mathematical formulation
"f as close to y as possible" is the same as finding the theta which minimizes the distance (euclidean) between them:
![[Pasted image 20220709203745.png]]

y - f() is the "residual" r, i.e. the distance between the hyperplane and y.


This can calculated directly by taking the derivative and setting equal to zero. This is the direct method and yields the psedoinvese solution.



### Problems
The analytical solution may be hard to compute due to:
* u may be extremely high dimensional
* f may be extremely non linear
* The dataset may have many many points
* theta may be in a very non-convex set

The LS estimate does not always exist! Example: If the domain of theta is an open set, there is no solution (ex: residuals = 1/theta)



