Complementary for navigation


[[INS]]: faster update rate, self contained, can be used for dead reckoning. Has own drift
GNSS: Slower update, relies on external signals, no own drift


## Uncoupled
Allow IMU to run for a period of time.

Reset navigation state by a known external reference

Only feasible for very high end INS.

A lot of information is lost since we do not use all GNSS information.

Also does not support bias correction


## Coupled
Continuously estimate [[INS]] errors.

Modern architectures use closed loop.

### Open loop
Correction is in the solution domain, i.e. as position, velocity and attitude corrections.

### Closed loop
Correction is in the INS measurement domain, i.e. accelerations and rotation rates per axis.
![[Pasted image 20220529145934.png]]




## Errors
At best we can make assumptions about the diagonal elements.
The off diagonal elements are unknown.

The [[Kalman Filter]] is only going  to work optimally if we provide full covariance information. This is usually infeasible with most GNSS receivers!

Tradeoffs:
1. **Ignore lack of information, use the variance values directly and set off diagonals to zero.** This will cause the system to trust the GNSS measurements too much and introduces correlated errors in the system
2. **Inflate the diagonal elements to compensate for the lack of full uncertainty information.** This will cause the system to trust the GNSS measurements less than it should, but will limit the effect of correlated errors.