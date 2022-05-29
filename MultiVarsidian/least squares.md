## Least Squares Estimation

![[multivar_exam_2022_l212.png]]

##### Basic Assumptions
Least squares is a parametric estimation techinique based on solely geometric interpretation of the dataset and a model. The underlying assumption is that the data was generated according to a model

$y_t = f(u_t, \theta) + v_t$ 

We are defining here a structure according to which our samples are assumed to be generated. This model takes inputs and produced outputs, as a function of both inputs and parameters. The parameters live in a hypothesis space, $\theta \in \Theta$ , and we have a dataset of N $y_t, u_t$ correspondences. The estimator is a function that takes us from the domain of the dataset to the hypothesis space. That is, it maps knowledge of some samples of input/output relationships into a set of parameters with some good properties. Note that in LS we are assuming to know the structure for the model. Note also that we are asuming some noise on the output, but we are not modelling that noise, indeed this method does not need any knowledge of this noise to be assumed, modeled or taken care of.

**Problem formulation:** find a set of $\hat \theta \in \Theta$ such that the dataset is best explained, ie so that $f(u_t, \hat \theta)$ is as close as possible to the $y_t$ for all $u_t$ and $y_t$.

This problem formulation leads to something which is very easy to understand and visualize, but not necessarily handle analytically although in some cases like [[linear least squares]], analytical solutions exist.


#### Geometrical Intuition
The vector of outputs y is a vector in $R^N$. The part of the dataset, which is the inputs, will be a set of $R^M$ vectors, where M is the dimension of the feature space.

$y = [y_1, y_2, ... y_N]^T$   

Each $\theta$ and set of N inputs will produce a vector in $R^N$. Keeping the set of u's fixed, and varying the $\theta$ will result in a manifold in $R^N$ (a collection of points which are continious because the model is continious). Thus for a set of parameters we map to a specific point on the manifold. We wish to find this point on the manifold which is closest to the y vector of the dataset. The manifold is a plane in the linear case and something curvy in the non-linear least squares case. 

![[multivar_ls_manifold.png]]

In the same manner, if we have come ot a set of parameters and vary now the inputs (maybe new data that we have to predict with the model) we shall also obtain a manifold in the dimension of the output vector size.

An alternative way of visualizing the LS problem is the "regression line" interpretation. This visalization considers not the higher dimensional space of the whole output vector, but plots all the inputs and outputs as many points in the dimensions of the features and outputs. Here, by varying $\theta$ we obtain different models/lines/curves in the space of inputs and outputs. Then, we are considering that each y will have some distance from the model in the y direction (actually can be an orthogonal projection in [[total least squares]]), and that direction will have a square. Then we can see that the best line is the one that minimizes the sum of these squares.

![[multivar_ls_line_regression.png]]

This visualization also shows well the concept of an over and underdetermined regression problem. We are estimating a set of parameters in the hypothesis space, and thus we need at least as many data-points as degrees of freedom in the hypothesis space. If we have more, the problem is over determined and we cannot get an exact fit (a fit for which the sum of squared residuals is zero). If we on the other hand have fewer datapoints than degrees of freedom, we will have infinitely many solutions which produce sum of squared resitduals 0. This is illustrated by the fact that a parabola model with $\theta \in R^3$  will have infinitely many solutions for theta which go through 2 data points. 

#### Mathematical Formulation
The LS fit problem can be formulated in terms of finding a set of parameters on the manifold in $R^N$ which results in the point on the manifold which is the projection of the dataset onto the manifold. Another way to write it is as a sum of squared residuals in $y_t$

$\hat \theta_{LS} = argmin \theta \in \Theta || y - \hat y||^2$, $\hat y = [f(u_1; \theta), f(u_2; \theta), ... , f(u_N; \theta)] \in R^N$ 

$\hat \theta_{LS} = argmin \theta \in \Theta \Sigma (y_t - f(u_t;\theta))$


#### Problems and Difficulties with LS
- Uniqueness of Solution - as mentioned earlier the LS problem might not have a unique solution depending on the properties of the dataset and how many parameters we are trying to estimate.
- Existence of Solution - this is a more theoretical subtle point. If one has an open set for the parameters, so maybe $\theta \in [0, 1)$ and the residual minimum is for $\theta = 1$, we can get arbitrarily close to 1 but still not be at 1 since it is not a part of our allowed hypothesis space. Then the solution of the LS problem will not exist. We need a compact (closed and bounded) set for hypothesis space.
- Ugliness of model - the model can be very non-linear and ugly. Projecting a point onto this, or finding a global minimum is in general not a trivial task. Combine this with a very high dimensional problem and we might having a bad time.
- Huge dataset - a huge amount of inputs and outputs will give rise to a problem which might be computationaly untractable. Especially if we are also having a non-linear function and if we are solving it on embeded hardware. 
