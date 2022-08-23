## Atomic clocks

GPS system time is produced on earth using an ensamble of 100+ clocks. These are linearly combined and weighted to produce a master clock.

These are all Atomic clocks and are used to steer the [[Satellite clocks]]


## User clocks
The user clocks in the [[User segment]] has a clock offset that is treated as an additional state in the system for observation. This is done since we can never guarantee the accuracy of any single user's clock.

We also often estimate the rate error of the local clock, since an oscillator with 1ppm frequency accuracy is $\pm$ 10 Hz at 10MHz (i.e. oscillator frequency), but  $\pm$ 1.6 kHz when upconverted to the GPS L1 band frequency. This error translates to $\pm$ 300 m/sec velocity error.

