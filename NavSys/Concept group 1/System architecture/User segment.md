## About
Completely separate and only takes data from the satellites.

## Problems and solutions
The "fancy signal" generated from the [[GNSS problems]] using [[CDMA]] and [[DSSS]] is **below the noise floor**. This means that we cannot see the signal in the time domain at any given time, but only as a "bulge" in the noise floor if we average over time.

This means that the receivers must be very low loss instruments and that we need to put in effort to recover the signal (we have a large search space.)

The user segment is thus responsible for [[Signal recovery]], and once doppler shift and code phase is known, is responsible for [[Signal alignment]]

