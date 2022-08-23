[[PVT]] estimations can very well be done with (E)KFs

## Assumptions
* Measurement noise is iid gaussian and uncorrelated with system state
* Process noise is iid gaussian and uncorrelated with system state
* Markov chain of order 1

Under these, the KF is an MMSEUE (minimum mean square error unbias estimator)

	A common tradeoff is to use a simplified error model with increased 
    noise power

i.e. a square peg can fit into a round hole if you make the hole big enough: We simply let unmodelled errors be noise


## Algorithm

![[Pasted image 20220529012803.png]]


3. Predict new state i.e. propagate with the transition matrix (which is constant in LTI) and the previous corrected state
![[Pasted image 20220529012817.png]]

4. Propagate the state covariance matrix
	* First term is "how covariance propagates into other states in the system"
	* Second term is additive process noise
![[Pasted image 20220529013016.png]]

	5. Calculate the measurement model at timestep k (which is constant 
    for an LTI system)
	6. Calculate the measurement noise covariance matrix (which is 
    constant for an LTI system)

7. Calculate Kalman gain
	* Takes the form F / (F^2 + R)
	* If the measurement noise covariance is large, the Kalman gain becomes small, and we will weigh the state estimate more
	* If the measurement noise covariance is small, the Kalman gain becomes large, and we will weigh the measurements more
![[Pasted image 20220529013452.png]]

	8. Get the measurement at the current time step

9. Correct the predicted state using the Kalman gain
	* The term inside the parentheses is the difference between the actual measurement and the predicted measurement using the predicted state and the measurement model
	* I.e. if the Kalman gain is high, we let the difference in measurement vs predicted measurement correct the prediction a lot (small measurement noise)
	* Likewise if the Kalman gain is small, we correct the state prediction less 
 ![[Pasted image 20220529013913.png]]
 
10. Correct the predicted covariance (calculate the posterior covariance)
![[Pasted image 20220529014206.png]]



## Asynchronous updates
The [[INS]] can be used in a prediction/update async cycle, where the IMU drives the predictions, while other measurements trigger the update cycle to correct predictions.
![[Pasted image 20220529014359.png]]


## Convergence
Given observability of states, we will have convergence.

Ideally, convergence will be smooth.
![[Pasted image 20220529014732.png]]


## Complexity
![[Pasted image 20220529015156.png]]
