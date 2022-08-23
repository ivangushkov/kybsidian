## Precise Point Positioning

Sort of a combination of [[RTK]] and [[Augmentation techniques]].

Relies on removing/modelling GNSS system errors to provide a high level of position accuracy from a single receiver.

	Aims to provide dm positioning over a giant geographical area - 
	sometimes the entire world.

![[Pasted image 20220523133327.png]]

PPP implements a strategy by using external data from far away to estimate errors and thus eliminate them.

	PPP convergence is between 20 and 40 minutes

That is, PPP converges much more slowly than [[RTK]].


## Practicalities
External data is used for correction and includes satellite orbits and clock corrections. When internet is not accessible, it may make more sense to directly use the satellite downlink to perform this.

Multi-frequency antennas are often required to eliminate ionospheric delay since a dm-precise model of the ionosphere that is valid globally is not feasible to have.

Residual tropospheric delay can be estimated when estimating position and other unknowns.

Modelling of tides is done.

The measurement model is:
![[Pasted image 20220523140636.png]]


Tropospheric path delay is part of M and zpd.

An [[Extended Kalman Filter]] is used for PPP estimation. The state vector is:
![[Pasted image 20220523140759.png]]

where zpd is the zenith path delay and N is non-integer carrier phase ambiguity.

The measurement model for the EKF is
![[Pasted image 20220523140844.png]]

