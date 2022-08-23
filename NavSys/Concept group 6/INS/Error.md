Aside from [[INS Bias]], there are other errors affecting [[INS]].

Errors in [[INS]] are generally unbounded, and may grow monotonically. 
![[Pasted image 20220529011847.png]]

	Only constant angular rate error makes the error grow unbounded


However, in the high end that can freely navigate for more than an hour, other interesting effects may occur. For example: Schuler resonance: Errors in the position solution interact with the gravitational model to form an oscillation in the solution and has a period of 84.6 minutes, related to the earth parameters.


	Adding error states usually comes with us adding noise terms for 
    their Gauss-Markov model.


![[Pasted image 20220529005420.png]]

![[Pasted image 20220529005504.png]]
Hysteresis: error depends not only on present state but also prior state.

## Cross axis coupling
Occurs when the three sensors are not orthogonal. This is a **very** important error source.

## Point of percussion
The physical sensors are not at the same point in space of the sensor. This will ideally be corrected for by the manufacturer, but is conceptually an axis offset error.


## Magnetic field sensitivity
Fiber optic and ring laser gyros can be affected by magnetic fields, since the electrons that are used in the system may take a curved path!
