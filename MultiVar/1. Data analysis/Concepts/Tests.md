![[Pasted image 20220710191345.png]]

False positive: type I error
False negative: type II error

#### Accuracy
	Total number of corrects (both true negative and positive) / total 
    tests
Overall, how often is the classifier correct?

A bit problematic for inbalanced dataset (not even spread of conditions), since the accuracy does not account for errors!


#### Prevalence
How often the "yes" condition occurs. The closer to half of the total instances are true, the more balanced the data is.
Since we usually don't measure the entire population, this is often estimated

#### Precision
	Number of true positives / total instances predicted as true

When you predict "yes", how often is it correct?

#### Sensitivity
	Number of true positives / total number of true

When it is actually "yes", how often does it predict "yes"?


#### Specificity 
	Number of true negative / total number of negatives

When it is actually "no", how often does it predict "no"?



# Aggregated scores
Sensitivity and precision can be combined into F1-score.
![[Pasted image 20220710192850.png]]

Note that this is symmetric for true positive and negative rates. If one of the error types is more important than another, a symmetric score should not be used.


# Multiple classes
If a test is not binary (like above) but instead contains multiple classes, we get a confusion matrix with performance indices.