Caused by the signal from the satellite taking multiple paths to the user.

The limit of the effect on the carrier is $\pm$ 1/4 cycle since the wave out of phase will cause a fade or the receiver will not track the weaker component of the multipath.

The effect will ultimately manifest as a ranging error, but note that this error can be both positive and negative! Depending on phase inversion or not.

On code (pseudorange) multipath can be tens of meters!
![[Pasted image 20220523102400.png]]

## Dealing with multipath
Multipath decorrelates over minutes for a stationary receiver due to the satellite moving overhead (angles and distances for multipath reflection changes).

If the source of an error is multipath then the same error will repeat for the same error whenever the satellite repeats its ground track (approx 24 hours).

The higher the chipping rate the smaller the ranging error, since the Mp effect is limited to  $\pm$ 1/4 cycle and the higher chipping rate limits the decorrelation range.