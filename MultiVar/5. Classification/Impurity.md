![[Pasted image 20220721013559.png]]

How uniform are our classes?


A measure of impurity can be found through Entropy:
![[Pasted image 20220721013637.png]]

Where pi is the empirical probability of class i

This can be interpreted with purity as "what is the probability of circle of square": The less the entropy the easier it is to predict circle of square


For two classes, plotting entropy vs purity, we will have max entropy at 0.5
![[Pasted image 20220721014122.png]]


## Information gain

By cutting the classes into segments, we get children that have different entropy than before:

Information gain = entropy of parent - average entropy of children.