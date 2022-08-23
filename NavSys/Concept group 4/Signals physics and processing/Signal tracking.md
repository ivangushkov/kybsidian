## About
For every satellite and every signal we operate a tracking loop:
![[Pasted image 20220522190444.png]]

Orange: Mixes and downconverts, and removes doppler shift frequency error, as well as the satellite LOS velocity. 

Phase and code discriminator is responsible for fine grain alignment and that we keep tracking the signal

The multiple-delay resampler is what generates the early, prompt and late signals