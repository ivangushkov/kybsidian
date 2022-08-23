
## Time differencing

Taking the difference of two range measurements from two different points in time. Assuming that clocks stay synchronized, the main contribution to the range difference is the satellite motion. Correcting for this motion leaves us with a measure of errors/ambiguities that are constant over time.

Remaining errors: Multipath and receiver noise.

If only applied alone, the impact of orbital and atmospheric effects increases over time. Also note that noise is increased as bias is decreased.


## Differential GNSS
Concept: two measurement sources are used, a reference and a "rover". 

	Reference is at a known location!

Most typical: broadcast pseudorange and range rate corrections from the reference to the rover for each visible satellite.

	Errors get larger for increased distance between reference and rover

The known position of the reference and known satellite coordinates yields a geometric range between the two:
![[Pasted image 20220523124428.png]]

The reference station then measures pseudorange and finds the differential correction:
![[Pasted image 20220523124700.png]]


## Notes
	Errors decorrelate over time and space!

[[Augmentation techniques]] utilize these concepts but have many many reference stations to create a network that can be used to map a large area with a gridmap of correction terms.


## Relative GNSS

#### Differencing receivers
If we only want to know our location very accurately in relation to some other receiver then we can simply difference the reference object to our location.

From these two measurements we can get deltas for pseudorange and phase.

Comparing to single receiver approach:

Delta pseudorange:
1. Reduces orbital and atmospheric errors
2. Eliminates satellite clock error.
3. Increases noise by sqrt(2)!

Delta phase:
1.  Reduces orbital and atmospheric errors
2. Eliminates satellite clock error.
3. Does not eliminate receiver clock error
4. Does not eliminate ambiguity
5. Increases noise by sqrt(2)!

#### Differencing satellites
By instead of using the same satellites with multiple receivers we can use multiple satellites for multiple recievers.
1. Errors due to **receiver clock** can be removed by differencing observations *between satellites*

## Double difference 
Utilizes the [[Double difference model]]
1. Errors due to orbit, satellite clock and atmospheric effects are removed by differencing observations *between receivers*.
2. Errors due to **receiver clock** can be removed by differencing observations *between satellites*

That is, using both differences allows us to remove many of the ambiguity terms. Double difference is used in [[RTK]] and is required for carrier phase ambiguity resolution.

	Assumes observations are taken at the same time epoch

Thus it requires tight synchronization for the receivers.

Double differencing also requires a "reference satellite", which is usually chosen as the satellite in view that is at the highest elevation angle (since this will be the least affected by atmospheric effects).

