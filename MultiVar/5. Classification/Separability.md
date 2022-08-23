There are different types of separability of data


## Linearly separable
The simplest. A straight line that divides the data in two regions.

More generally, it will be a hyperplane wTx + b. This is the solution that the [[LDA]] finds.

This can be interpreted as "weighing x and adding a bias yields a number in R".

Everytime we select a w and a b, we define a hyperplane.

the x such that wTx + b = 0 defines the intersection! 

The intersection is of lower dimension

	The intersection with the domain and the hyperplane are two 
    different things!


Linear separability when y(wTx + b) >= 1

This holds since the x and y will have the same signs (+ maps to + and - maps to -, i.e. always positive)

