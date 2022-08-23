## Concept 
Add local filters for pre-filtering for the sensors that benefit from this.

This is a concept that allows us to divide the problem space:
* Avoid having to make a model that relates all observations to all system errors
* Instead we can logically partition the models in to sensor specific filters
* There are also potential performance benefits to this (reduces the n states in the KF when correcting)
![[Pasted image 20220529152455.png]]


