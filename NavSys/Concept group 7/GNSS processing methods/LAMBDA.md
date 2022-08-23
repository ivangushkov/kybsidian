## Least Squares Ambiguity Decorrelation Adjustment

	Reduce search space by decorrelation adjustment!

1. Decorrelate the second ambiguity from the first
![[Pasted image 20220523132001.png]]

2. Decorrelate the first ambiguity from the decorrelated second
![[Pasted image 20220523132007.png]]


This preserves the number of candidates, but they can be found more efficiently.


## Geometry of LAMBDA
![[Pasted image 20220523132119.png]]

By decorrelating the measurements we reduce the search space from covering a 6x6 grid to covering a 4x4 grid.


## Verification
The sum of square residuals is used to calculate a set
![[Pasted image 20220523132308.png]]

By adding the floating solution we obtain a total [[Least squares]] solution:
![[Pasted image 20220523132334.png]]

By thresholding the ratio of the second smallest to the smallest omega total we can check for convergence:
![[Pasted image 20220523132411.png]]

