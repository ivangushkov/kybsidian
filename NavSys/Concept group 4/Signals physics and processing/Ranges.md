## Range

For Time of Flight application, if we have perfect clock synchronization between the transmitter and the receiver, we can directly calculate the range between them by using the known travel speed of the carrier signal

## Pseudo range

When the transmitter and receiver are not synchronized in time, there is a clock offset that will translate to a range error between the two. The pseudo range thus includes a clock offset term and perhaps also other effects.

![[Pasted image 20220522191532.png]]

Rp is the actual range and  $\rho$ is the pseudo range:
![[Pasted image 20220522171613.png]]

Note the delta clock term

* T is tropospheric delay
* The next term is an error that comes from the clock offset of the receiver and the satellite relative to "true" constellation time
* Alpha f STEC is the [[Ionosphere]]ic delay term
* Kpr and KPs are the receiver and satellite equipment group delay
* Mp is a [[Multipath]] error term
* Epsilon p is receiver thermal noise (electronics noise)

## Errors
The different effects above are described in [[Range accuracy]]

The errors in range are not equal in 3D: height/radial error appear most strongly in measurement, which means that the [[Control segment]] can estimate them easier (but again, affects the range estimate more).

Cross and along track are opposite: harder to measure but affects the user less.