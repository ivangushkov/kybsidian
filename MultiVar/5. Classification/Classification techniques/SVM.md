## Support Vector Machine
Relies on the intuitions from [[Separability]]

The smaller the w, the less the projected variability on x varies in y:
![[Pasted image 20220720232013.png]]
This links back to the [[Bias variance tradeoff]]. We cannot make w arbitarily small without sacrificing performance, i.e having the samples be placed in the wrong section of the cut


### Margin
A margin associated with a plane (w, b) is the minimal distance between a sample and the plane


### Optimal separating hyperplane
This is the hyperplane which induces the maximum margin (i.e. maximally distant from the closest points), which is equivalent to the "least slanted". This is a **very** different 
separation rule than [[LDA]]!

For the above example:
![[Pasted image 20220720232826.png]]


	The separation rule is defined by the closest points only!!!!!!!!

This is VERY nice, since we can be "very certain" about points that are well within a class, but the edges towards each class is very meaningful. That is, by reducing the slant we make a [[Bias variance tradeoff]] to get less variability. We are using less data, only using global effects etc.


### Support vectors
The points that "are touched" by the hyperplane. The solutions to the SVM problem is a convex optimization problem:

![[Pasted image 20220720233208.png]]

## Non separable data
In this case, we **cannot** find a solution like before. 

However, we can reformulate the optimization problem to "admit that we can be wrong sometimes". Ideally the yi(wTxi - b) term is one, but will be less than 1 for erroneous classifications. This allows us to "ignore" the misclassified elements

We also perform [[Regularization]], where the lambda decides how much to promote a small margin, which implicitly decides how many elements may be misclassified

The problem then becomes to minimize

![[Pasted image 20220720233404.png]]


The alternative approach to non-separability is the [[Kernel trick]]:
![[Pasted image 20220720235438.png]]
