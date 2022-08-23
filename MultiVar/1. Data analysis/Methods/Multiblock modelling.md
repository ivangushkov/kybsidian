From single [[PCA]] to multiblock [[PCA]]

# Setup of multiblock model
![[Pasted image 20220718021323.png]]
Generated from
![[Pasted image 20220718021527.png]]

We have multiple blocks of data, f.ex one from each sensor.

We *could* do single [[PCA]] on each of the Xi's, then make a matrix where the columns are the score vectors, then solve using [[NIPALS]] or [[SVD]]


# Regression 
This can also be done for regression, like [[PLSR]] for each block.
![[Pasted image 20220718021654.png]]



