## Concept
All electronic devices add noise. That is, only using single step components will not allow us to improve SNR, only worsen it.

Thermal noise manifests itself as white noise in the measurements. This factor is very difficult to deal with, so its influence is minimized by careful design of the [[User segment]]. If we cannot do this we may use longer periods of [[Coherent integration]], but this has its own limitations.

To "set the noise floor" we may have the first step be a high gain low noise amplifier. From the *Friis formula* all subsequent noise terms or losses are divided by the first stage gain!