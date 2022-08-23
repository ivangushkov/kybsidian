To resolve integer ambiguities in the [[Double difference model]], a search space is used. 

The first LS solution estimates ambiguities as real/floats, which is why the first double-difference solution is called the "float ambiguity solution".

Estimate one N for every satellite in view:
![[Pasted image 20220523131412.png]]

![[Pasted image 20220523131453.png]]

Challenge: Brute force search requires (search space range)^(n satellites in view - 1) combinations. This can get out of hand very quickly, and we would like to optimize this search.


## Strategies
![[Pasted image 20220523131811.png]]

