


Satellites in the [[Space segment]] have clocks,  but these are exposed to radiation, thermals and vibration. The clocks are getting better :)

The [[Control segment]] steers these clocks slowly over time, so to avoid discrete jumps, since 1ms difference is 300km of error.

The satellite clocks are however allowed to drift up to 1 ms, but to use this in navigation, the [[Control segment]] also uploads a polynomial fit to this drift.

![[Pasted image 20220522180401.png]]

Since we dont want to discretely correct for the clock drift all the time, we can instead model and account for drift. Note that this model cannot account for all daily variation that happens due to sun exposure, but is likely modelling Rubidium/Cesium variations.

af2 term is often zero, leaving a linear fit, which will only be valid for a short amount of time. This can be problematic since the satellite is only updated once/thrice per day.

The satellite clocks are steered to system time, but we still have 
to correct for it using data from the [[Ephemeris]]


## Broadcast
For timekeeping ([[Time reference]]) the satellites also broadcast estimates for time offsets between constellations. I.e. Offset between GPS and Galileo is GGTO. This can be used in conjunction with estimates to improve accuracy (i.e. calculate on the fly)

![[Pasted image 20220522182043.png]]