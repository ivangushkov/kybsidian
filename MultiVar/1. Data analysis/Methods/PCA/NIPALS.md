# Nonlinear Iterated Partial Least Squares
Iterative algorithm.
Estimates one PC at a time
Handles missing data directly
Efficient when both rows and cols are high in number


## Graphically
![[Pasted image 20220713205757.png]]

Calculate p and t back and forth until t does not change much. Make sure to normalize p's to length 1! (1) - (3)

After each component converges, we remove the contribution of this PC from the data, and go again. (4)


## Mathematically
![[Pasted image 20220713205939.png]]