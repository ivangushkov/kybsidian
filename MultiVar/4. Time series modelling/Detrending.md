There may be effects that vary around a trend, i.e. sinusoid about a slope


The original data will not be stationary, but by "detrending", i.e. removing the trend, the resulting data can be stationary!


Common approach: Low order, long time constant [[Autoregressive model]], specifically ARX:
![[Pasted image 20220718164414.png]]
The simplest ARX is
**![[Pasted image 20220718164532.png]]

If e is gaussian, the solution here is the [[Least squares]] solution



The ARX models are smooth, and embeds exponentials, lines etc etc, and can be tuned to have very high time constants, i.e. constrain poles to be close to the Im axis.




	It is important to retrend after making the model, so to stay true 
    to the actual data

