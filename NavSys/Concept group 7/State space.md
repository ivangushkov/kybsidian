## GNSS state space

$z = Hx + v$  where z is the measurement, and is modelled as a linear state model plus additive noise. H is the observation matrix.

$\sigma ^2$  is the variance of each measurement, and for the entire state space we will have a covariance matrix **R** or $\Sigma_z$  

The state estimation part can be written as 
![[Pasted image 20220522174408.png]]

where the state covariance matrix **P** can be written as 
![[Pasted image 20220522174505.png]]



## Observation state vs state space
![[Pasted image 20220523141618.png]]

[[RTK]] uses OSR while [[PPP]] uses SSR.

#### OSR
Gives corrections in the form of all available observations.

Converges much faster than SSR.

#### SSR
Attempts to estimate the "true" values given a set of observations, and transmit these estimates as corrections.

Scales to a much larger area than OSR.

![[Pasted image 20220523141524.png]]