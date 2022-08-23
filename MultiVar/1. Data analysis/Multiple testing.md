Ex:
A test has 5% chance of false positive (type I error)
If 100 tests all negative, the expected number of errors is 5

If the tests are statistically independent from one another, the probability of **at least one incorrect rejection** is 99.4%

"At least 1" is different from the false positive rate!

## Intuition

The type 1 error is not constant when redoing the test over and over again.

The more inferences are made, the more likely we are to have at least one erroneous inference!



## Correcting for this
1. Use the Bonferroni correction (adjusted p-value) (most used)
2. Use the false discovery rate 
3. Family wise errors