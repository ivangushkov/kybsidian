Create a simpler model from a complex model

Aim is to invest computational resources to develop fast approximations of demanding models

![[Pasted image 20220719112309.png]]


Green is [[DoE]] to find input-output relations.

By creating the red, we circumvent the blue path.


The [[DoE]] is done by:
1. Perturbing parameters in the physical/simulation model
2. Estimating the sensitivity of the parameters (incl. interaction and square terms)
3. Establish IO
4. Find optimal settings given constraints
5. Predict output not using the complicated model

We use Latin hypercube designs where each dimension is cut into N sections where N is the # of sampling points. Only one point is put in each section. This is optimization by distance in order to fill out the factor space