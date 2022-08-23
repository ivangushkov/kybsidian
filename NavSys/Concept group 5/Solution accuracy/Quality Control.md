## Concept
Error exclusion in the measurements themselves. Common error is NLOS (Non-line of sight error)


## NLOS
NLOS happens when the LOS signal is blocked but the reflected multipath reaches the antenna. If the reflection surface does not attenuate the signal much, the multipath signals may actually appear as valid signals from power level alone



## Satellite clock failures
The [[Space segment]] carries multiple clocks, but if they all fail then the ranging measurements will be all wrong.


## Improperly executed orbit maintenance
If the orbit needs to be adjusted using thruster burn, the satellite needs to be marked as unhealthy, since this is a very disruptive process. If this is not done, the [[User segment]] may report large errors. Additionally, the [[Control segment]] may upload wrong or misclassified orbital data, which can especially be the case after maintenance. 


## Signal meaconing (repeaters)
If repeaters are set up improperly, the repeater may actually be picked up as a separate signal *in addition to the actual satellites*. 


## Quality control methods
multiple t-testing and chi-square thresholding can be used to hold out the worst measurements.

The thresholds depend on both measurement uncertainty and geometry ([[DOP]]).

Plotting the expected measurement vs actual measurements makes this obvious:
![[Pasted image 20220523114117.png]]


## Quality control of [[PVT]]
Positioning error is simple enough - length of the path changes for a reflection path.

Velocity error however, the velocity error depends on both user/satellite error as well as the geometry of the problem.
