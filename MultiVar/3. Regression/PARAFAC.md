# PARAFAC
Instead of having [[Scores]] and [[Loadings]] we have "modes", and we decompose into 3D, 3 modes (A, B, C)
![[multivar_n_way_unfoldings.png]]

Typically used for sensor data that has 2 dimensions.

The solution boils down to [[Least squares]] by iteratively assuming the parameters in two modes are known, and estimating the unknown set of parameters in the third


![[Pasted image 20220718022651.png]]

Initializing B and C is done randomly.