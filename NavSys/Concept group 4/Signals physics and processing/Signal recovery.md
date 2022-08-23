## Signal recovery
The search is made over time *and* frequency. For this reason, 
* The codes should ideally decorrelate over frequency shift
* We need to determine the doppler shift of the satellite
* We need to determine the "code phase"*

\*For [[CDMA]] this means the alignment within the 1ms repetition window. 

Granularity of the search space depends on:
* Sampling rate
* Oscillator quality
* [[Coherent integration]] time, i.e. the amount of time we add up signal without squaring to boost SNR
And is a consequence of the fact that mathematical operations take clock cycles to perform: MAC (multiply and accumulate) scales with sampling rate and doppler range, but exponentially so with coherent integration. Much more of a problem before.

To recover the signal we may multiply the incoming measurements with the [[Pseudo Random Noise]] used in the [[CDMA]] scheme.

Once the PRN code has been acquired we need to find the phase of the signal, i.e. the [[Delta range]]

After recovering a signal it is fit for [[Signal alignment]]