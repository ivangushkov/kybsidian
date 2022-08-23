The [[Ranges]] suffer from error terms, as presented in said page. More details below:

## Tropospheric delay
A delay in speed of light caused by water droplets in the troposphere. It is usually expressed as a "zenith value" i.e. how much we would expect directly overhead. Non-overhead mesurements are projected.

It is divided into wet and dry.
Dry: majority of the error and is well modelled to high accuracy
Wet: less than 5% of the error and depends on the meteorological conditions along the signal path.

Lower elevation yields more air for the signal to pass through, thus more error.

## [[Ionosphere]]ic effects

STEC: Slant Total Electron Content and expressed the amount of charge encountered by the signal as it passes the ionosphere on the "slanted" path from satellite to user.

Two methods to calculate:

1. Use a model to calculate effects at your own location
2. Use [[Augmentation techniques]] which broadcast grid models which can then be interpolated by the user.

One method to estimate (BETTER!! (usually)): 
	The ionospheric delay is frequency dependent - By using two carrier frequencies from the same satellite we can then isolate the effect of the ionosphere and thus remove it from the measurements. This is about 99% effective. 
	The downside to this approach is that it requires a dual frequency receiver, which is more expensive. It also increases the noise level of the measurements - so we are trading bias for noise. Lastly this approach is sensitive to "cycle slipping" - where the [[Signal tracking]] loop loses lock but relock a few cycles away. These can be hard to detect since it is a small error. Ironically a more active ionosphere increases the chance of cycles slipping.


## Group delay
The satellite equipment itself introduces a delay, and this is broadcast by the [[Space segment]]. The user error is not broadcast but can be calibrated away by "leveling", i.e. leaving the receiver out for long enough to have seen "zero ionospheric delay", thus only measuring group delay of the user equipment.



* Mp is a [[Multipath]] error term
	* Goes to zero when there is nothing to bounce off of
	* When there are objects that the signal can bounce off, the measured peak is not the actual peak, but one that is offset by some bias caused by the longer path.
* Epsilon p is receiver thermal noise (electronics noise)

## Errors

The errors in range are not equal in 3D: height/radial error appear most strongly in measurement, which means that the [[Control segment]] can estimate them easier (but again, affects the range estimate more).

Cross and along track are opposite: harder to measure but affects the user less.