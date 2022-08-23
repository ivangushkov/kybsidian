Supervised methods with an objective function to discriminate between classes!

[[PLSR]]-DA , [[LDA]], [[Logistic regression]], [[SVM]], [[Clustering]], [[ANN]], [[CNN]], [[Random forest]]




## PLS for classification
PLS discriminant analysis can be used as a classifier when the y variables is cont, but can also be used when y is categorica

[[PLS-DA]] predicts a sample as belonging to one group or another based on prediction values close to zero or one! 

Close to 0: not in the group
Close to 1: in the group
![[Pasted image 20220720005111.png]]

we can find distributions about y from the [[Cross validation]]
![[Pasted image 20220720005539.png]]

we can use the probability of a sample belonging to a class this way. This avoids the dilemma of a variable getting the value 0.5