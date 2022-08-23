Simplest strategy

1. Build a model for each class
2. Samples inside the critical limits for each class (self defined) are "accepted"
3. Others are "rejected" - not classified

Drawback: The individual models dont know about the other classes! No objective function to discriminate between them!

Methods: [[PCA]], [[ICA]], [[Clustering]], One-class [[SVM]]


## PCA for classification
SIMCA

Use leverage and F-residuals as criteria (5% default)
one PCA model per class

Note that a sample may be classified into one, multiple or none of the classes

Also common to highlight the variables that are important for classification


