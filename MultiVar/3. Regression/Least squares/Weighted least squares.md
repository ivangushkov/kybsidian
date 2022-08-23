# Weighted Least Squares
If the power of the noise varies for different measurements, then using the normal [[Least squares]] is meaningless, i.e. we should weigh them differently!

Example: Two sensors produce measurements - one that is highly accurate, and one that is not. The accurate sensor should be weighed more!




## Geometrical intuition
Instead of a euclidean projection from the data point to the [[Manifold]] that f forms, we wish to use Malahonobis distances to weigh components differently according to some [[Statistic]].

## Mathematical formulation
![[Pasted image 20220710122128.png]]
Similar to the normal LS, but with a weight for each sample. Note that if the problem is linear, separable and unconstrained, we may use the weighted normal equations.

Note that if the noise is homoskedastic (see [[Skedacity]]) then $w_t$ is constant, and will thus be optimized away in the solution of the minimization problem. Thus, the WLS solution only differs when the noise is heteroskedastic.