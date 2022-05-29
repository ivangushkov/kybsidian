## Linear LS

#### Basic Assumptions
- Separable problems - these are problems which are linear in the parameters, but not necessarily in the inputs. The inputs can be transformed in some strange way before they see the parameters, but so long as we know the transformations, we can map the inputs into features and have a linear problem from there on.
- Unconstrained Parameters - we are looking here for parameters in $R^N$, where N is the dimension of the feature space. Meaning we are not constraining $\theta$ to a region of $R^N$. This is not true in general, we can constrain it which will lead to constraints on which parts of the manifold we can reach. 
#### Geometric Intuition
The separable problems assumption will lead to a linear matrix problem, where we are solving for the dataset vector given a feature matrix and parameters. This means we are looking for the point on the hyperplane defined by the combination of feature vectors which is closest ot the dataset.

![[multivar_linear_LS_plane.png]]


#### Mathematical Formulation
The assumptions of separable problems and unconstrained optimization will lead us to the normal equations. Recall that we are minimizing norm of the orthogonal projection of the data onto the hyperplane which the feature matrix spans. Then the computation looks as follows:

![[multivar_normal_eqs_crunch.png]]

If $\Phi^T \Phi$  is not invertible, we have to use the [[matrix pseudoinverse]] which will find in the real span of $\Phi$ the point which has an orthogonal projection of the dataset y.

#### Difficulties and problems
- Existence of Solution - the normal equations are not in general solvable for constrained $\theta$. That is, we can still find a solution but it is not guaranteed to be in the valid hypothesis space we have defined.
- Purely Geometric - the LS solution is purely geometric and takes every sample at face value. It might be that we have heteroschedastic noise, meaning sometimes we get shoot noise which will produce an outlier that we can safely ignore. The solution might be [[weighted least squares]].


