For us, a dyn system is something that produces an output based on inputs under the effect of disturbances.

## Modelling 

ydot = f(y, u, theta)

u are our inputs (we can choose), y are our outputs/measurement (we can choose).

Modelling is determining f and theta

In our case: ODEs as models for systems whose signals are time series.

PDEs are infinite-dimensional state spaces! Thus, to do [[System identification]] on PDEs, we need to discretize

	When we as engineers create models, we worry about the "usefulness" 
    instead of making things as "correct to reality" as possible

More complicated models will yield controllers that are harder to tune (more variables), and risks high variance, again the [[Bias variance tradeoff]]