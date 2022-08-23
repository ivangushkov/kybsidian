How to take the measurement from [[INS]] and turn them into a navigation solution.


## Simplified version
![[Pasted image 20220528155750.png]]
0. Initialization - we must tell the INS where it is.
1. Integrate a new angular rate measurement to get an attitude estimate
2. Use a new attitude estimation to transform the specific force from the sensor frame to the navigation frame (i.e. earth)
	* How we measure *g* will depend on our orientation
3. Correct the specific force with the gravity model
4. Integrate the corrected specific force to calculate a velocity update
5. Integrate the updated velocity to calculate a position update.
Repeat to step 1

## Full version
![[Pasted image 20220529002227.png]]
Minus is the prior, and plus is the posterior.

#### Attitude
Small angle small timestep approximation to the matrix exponential
![[Pasted image 20220529002451.png]]

#### Specific force
![[Pasted image 20220529002705.png]]
or
![[Pasted image 20220529002713.png]]
((velocity in the inertial frame))
#### Velocity
![[Pasted image 20220529003034.png]]
Approximation ^. Gravity model is assumed as a function of latitude and height, but more accurate/long range systems use longitude and time.

#### Position
![[Pasted image 20220529003223.png]]

## Notes
We want a short interval between IMU measurements, since we are blindly integrating, i.e. using taylor expansions to linearize where we neglect square and higher order terms. 

Neglecting order 2 and higher terms means that we are assuming constant value of the rotation matrix over the interval, and taking the average of it (i.e. the midpoint)
![[Pasted image 20220528161550.png]]

