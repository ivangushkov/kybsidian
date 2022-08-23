## Uncertainty in closed loop
Synchronization issue: 
When in time did the GNSS measurement occur relative to the output rate of the [[INS]]?
This problem is shared by any two systems sharing observations of a common state.

[[INS]] usually has its own running internal clock, this clock produces measurements at the selected rate and is **not** synchronized to GPS time.

Solution: [[GNSS-PPS]]



The choice of coupling depends on what equipment and resources we have!

## Loosely coupled
Takes place in the position domain: GNSS receiver provides position and velocity which is fed into the [[Kalman Filter]]. In this configuration we preserve

* GNSS solution only
* [[INS]] solution only (open loop)
* [[INS]] solution corrected (closed loop)
* Integrated navigation solution

Problems: Observability - since we require a full solution we require a minimum of 4 satellites.
![[Pasted image 20220529150452.png]]

## Tightly coupled
Work directly on the pseudorange and phase rate from each individual satellite. This then means we remove the bound of 4+ satellites.

	We still require 2 satellites minimum since the first will be used 
    entirely to estimate clock error in the receiver - only the second 
    is a measurement

![[Pasted image 20220529152854.png]]


At each measurement epoch we use the current [[INS]]/[[Kalman Filter]] position estimate:

* We estimate what the pseudoranges and pseudorange rates (doppler/phase) would be
* The measurements are the pseudoranges and phases directly

The problem of not full covariance matrix is removed: We instead have to estimate uncertainty in each pseudorange measurement, but dont typically have cross-[[correlation]] terms. Use instead a combination of SNR and elevation angle and satellite/signal type!

	Since we are introducing range and range rate as states, we also 
    need to include the clock error and clock error rate as part of the 
    state space

Clock error is a bias that affects range and clock error rate is a bias that affects range rate


## Deep coupling
Where tight coupling stops at estimating pseudorange/rate, deep coupling extends this to correlator state which estimates code phase and code phase rate for every satellite.
![[Pasted image 20220529153536.png]]

Feedback to the integration algorithm is conducted via digital spectrum samples. 

This approach makes [[Signal tracking]] and [[Signal recovery]] much more robust and rapid, since the [[INS]] and [[Kalman Filter]] acts like a filter that reduces the bandwidth of the feedback needed, since the search space for codes is limited in feasibility by the predicions of the filter.8

Reduced bandwidth lets through less noise, i.e. we are tracking a small signal residual rather than the full signal dynamics, and thus gain robustness.

The drawbacks are that the system is much much more complex and requires more signal processing.

Additionally we need full control of the GNSS receiver, so we cannot do this with any old receiver we buy off the shelf.