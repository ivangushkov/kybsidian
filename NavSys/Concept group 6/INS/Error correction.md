[[Error]]s in [[INS]] can be corrected, but beware!

![[Pasted image 20220529010350.png]]

Scale factor errors can be absorbed in the cross axis error, but this is still 18 error terms.

## Computational complexity
O(n^2) or O(n^3) depending on what stage of the estimation process we are in, and exponentials catch us very fast!

	Adding error states usually comes with us adding noise terms for 
    their Gauss-Markov model.

Thus, to make all states converge we either require more time or more information


## Observability
Some errors require certain maneuovers to separate their effects, thus making them observable.

	Constant bias and scaling factor are not observable from a singular 
    measurement


Figure 8 motion can be used to separate out effects



## Calibration scheme
1. Start static so we can perform basic [[Bias correction]]
2. Begin linear motion to help with heading resolution
3. Begin figure 8 motion
4. Come to a stop and repeat step 3 as many times as feasible