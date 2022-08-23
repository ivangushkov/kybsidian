## Concept
The longer we accumulate signal samples the higher signal to noise ratio we will achieve, given that the noise is uncorrelated.

## Coherent integration
Add up noisy samples over time

n samples of white noise, the expected value of the sum is zero, but the magnitude is not:

$E[nsamples] = 0$
$E[abs(n samples)] = \sigma \sqrt{n}$   i.e a random walk

The power of a signal is related to the square of the magnitude.
Ex: the power of a sinusoid is A^2 / 2 which gives an SNR = A^2 / sigma^2 * n

	Coherent integration of n samples boosts SNR by *n

 

## Non-coherent integration
Add noisy samples in batches with a squaring operation - not sign preserving and us referred to as the "squaring loss"

	Non-coherent integration of m blocks boosts SNR by *sqrt(m)



## Choice of technique and limitations
Since coherent integration boosts SNR more, it is preferable when wanting to boost SNR. However, bit edges are problematic, since if a 1 and 0 fall under the same integration period, they will cancel out!

In GPS we have data bits at 50 Hz which means that data bits stay the same for 20ms, which means that we can coherently integrate these signals if we know the bit alignment, which we get from [[Signal alignment]].

Any time difference produced by the oscillator at the unit performing the coherent integration will cause frequency errors. Thinking of the signal as a vector in the complex plane, any frequency or doppler error will cause the signal to rotate in phase.

This is a "relative timing error" that limits the coherent integration period. Crystals in most electronics in the [[User segment]] can support errors of 5Hz over 100ms period, which translates to at the 5Hz / ... at the 10MHz band since the 5Hz is at the upconverted L-band frequency.

Since the [[User segment]] likely will move and cause a doppler error just by existing, plus the 20ms limitation for the GNSS signals, we usually limit coherent integration to 10-20ms anyways.


## Hardware
Quartz is limited to around 100ms coherent integration
Atomic clocks can support 10s of seconds.