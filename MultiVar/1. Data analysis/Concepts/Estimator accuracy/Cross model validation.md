An extension of [[Cross validation]] where we have more than 1 layer of folds, i.e. for two levels we have an outer loop that does a [[Splitting of datasets]], and an inner loop that again splits the outer fold into inner training/valid sets

We use the model found in the inner loop when doing the outer loop training!

![[Pasted image 20220717234320.png]]

