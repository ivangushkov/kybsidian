## Problems and solutions
0. Need to be resistant to unintentional interference but also coexist with other systems.
1. Need to receive from multiple satellites simultaneously
2. Need to be able to acquire the signal from an unknown state (i.e. no initial position)
3. Need to be able to decode orbital data from the signal
4. Need to be resistant to ionospheric effects
6. Need to be insensitive to antenna orientation
7. Need to be received on earth with very low power budget on the satellite



## 0
[[DSSS]] - by multiplying the narrowband 50 bps satellite signal by the high rate chipping signal we spread the signal over a MHz of spectrum. 

This spreading means that the PSD (Power Spectral Density) is lower, i.e. less interfering with other users.

Since the user also "de-spreads" the signal upon receiving, then any narrowband interference will be spread out by the same amount.

## 1
Solved in different ways. GLONASS uses [[FDMA]] while GPS/Galile/Beidou use [[CDMA]]. 

## 2
When signal is strong and with known freq, lock is easy. We have neither:
* Signals are weak due to (6)
* Doppler motion of the satellite can shift frequency of several kHz
* Local oscillator in the user equipment may be relatively low quality. Ex 10ppm uncertainty is 16kHz of uncertainty.

Solution: Pre-multiply the weak signal to be searched for with a long sequence of known 1s and 0s that repeats at a known interval. For GPS coarse acquisition this is [[Pseudo Random Noise]]. 


## 3
System designed when each device having access to high speed internet connection was a dream. All data needed to calculate the satellite/own position thus had to be included in the data stream from the satellite.

This needed to be done while keeping data rate low, since the Shannon information limit says that more data needs more power for reliable transmission. This is packed into the [[Almanac]] and [[Ephemeris]]

## 4
See ionospheric effects in [[Ionosphere]]. Due to the frequency dependent delay, each satellite transmits at least two frequencies, since time delay translates to a ranging error.


## 5
If the transmitter and receiver is linear polarized (i.e. electric field swings along one axis) and they are orthoginal to eachother, the signal will lose almost all its power. This may happen for a rotating user.

Solution: Circular polarization - electric field is split so to be two waves swinging on orthogonal axis. Regardless of user/receiver rotation they will receive half of the signal power.

This solution is also good  wrt Faraday Rotation - that signals passing through a charged medium - here [[Ionosphere]] - causes the polarization of the signal to rotate.

## 6
A consequence of size and power limits. Rocket equation: exponential relationship between rocket size. Solar is the only realistic option since nuclear is expensive and reserved for deep space probes.