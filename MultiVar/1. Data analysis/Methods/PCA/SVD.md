# Singular Value Decomposition
Direct algebraic solution
Often estimated from the smallest covariance matrix X^TX or XX^T

If we are either missing values or rule of thumb over 250 cols, use [[NIPALS]]




## Theorem
![[Pasted image 20220713210221.png]]

The diagonals of Sigma are the [[Singular values]] of X (often sorted in decreasing order)
The columns of U are the left [[Singular vectors]] of X
The columns of P are the right [[Singular vectors]] of X

[[Scores]] = U * Sigma
Loadings = P