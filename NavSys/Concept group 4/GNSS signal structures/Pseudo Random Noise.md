## Pseudo Random Noise
Part of the [[CDMA]] scheme.
Allows for searching and finding of the otherwise very very weak GPS signal.
Allows for partial synchronization.

Made of "chips" i.e. binary "bits" but not bits since they do not contain any information.

Note that +1 and -1 are used instead of 1 and 0 when sending data.

## Concept
Multiply an outgoing weak signal with a string of 1s and 0s. The receiver can then match any received signal with a generated copy of the same binary string used by the transmitter through auto[[Correlation]]: Whenever something lines up, there will be a sharp peak at zero.

Note that this requires that the codes used have very low autocorrelation aside from at zero.


## Example
GPS L1CA has a sequence length of 1023, and a chipping rate of 1.023 MC/s which gives a period of 1ms


## Implementation
A pair of shift registers are used, their outputs are multiplied to generate codes. The shift register has length n and can generate a 2^n - 1 long non-repeating sequence. I.e. a 10 bit reigster produces a 1023 bit maximum length sequence.

When used as a carrier / spreading code it reduces impact of interference and when used with an encryption sequence it provides spoofing protection.

![[Pasted image 20220522170912.png]]



