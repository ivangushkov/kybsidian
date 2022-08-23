# The likelihood function
The purpose of the likelihood function is to capture the distribution of the measurements


## Geometrical intution

For example, a normal pdf for measurements + noise is a bidimensional function.
![[Pasted image 20220710124106.png]]

Assuming sigma constant, we can plot this function in 3D: with y, theta and the value of p as invidividual axis.

The probability density function arises from this graph as the intersection between the manifold and a plane for a specific constant theta. That is, the expected distribution of all measurements for a given value of theta.

The likelihood function can be found from the same graph using the intersection between the manifold and a plane from a specific constant y. This function represents the likely parameter of theta that would have caused a specific measurement to take on this specific value.


### Function
![[multivar_likelihood_pdf_bivariate.png]]


### PDF
![[multivar_pdf_cut.png]]


### Likelihood
![[multivar_likelihood_cut.png]]



