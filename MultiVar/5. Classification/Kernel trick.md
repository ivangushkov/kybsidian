# Kernel trick

**VERY IMPORTANT CONCEPT**
![[Pasted image 20220720234100.png]]

If the data does not have [[Separability]] in the normal space we define it in, can we define some mapping to another space where the data is separable?
Usually done in a VERY high dimensional space.


Note: [[SVM]] relies on inner products, wTx. 

Mapping x -> x' means changing the inner product wTx to w'Tx'. This inner product is thus also in a higher dimension.


	Instead of doing inner products in the original space, do them in 
    the augmented space

This however, comes with a caveat: Higher dimensional inner products are more difficult/expensive to compute.

The solution:


## The trick
The inner product of data in R2 is a function on R2 **ON THE ORIGINAL DATA**

Ex:
![[Pasted image 20220720234543.png]]


	We don't need to store the samples in the mapped space or do the 
    computations associated to the mapping!

Instead, we just do a nonlinear product **in the original space**.

This works for infinite dimensional mapped spaces! This is the case for an exponential, since the taylor expansion of exp() is infinite
![[Pasted image 20220720235327.png]]


## The problem
There is no theoretical tool to find the "best" kernel! This is sort of a [[Model Order Selection]] problem... This again links into the need for [[Model Validation]] and [[Bias variance tradeoff]]...

Use the parsimonity intuition.

The most used kernels: 

Linear, polynomial, sigmoid, radial basis function

	Always validate!


