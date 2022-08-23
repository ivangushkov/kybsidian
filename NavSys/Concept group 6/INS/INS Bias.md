
Small bias and/or errors will accumulate over the integrations in [[Mechanization]]. 
	
	Bias leads to exponential error growth in the position output

Accelerometer bias is integrated twice. If the bias is modelled as constant in the small time instant of [[INS]] updates, this will be a square error in position

Gyro bias causes a sinusoidal modulation of the gravity mapping. Over short time instants this is a slope, and a linear increase in an acceleration mapping leads to cubic growth after integrating twice



Bias is divided in two parts: Turn on and random walk

## Turn on
Constant bias in the output of the sensor. Can change between power cycles of the sensor (thereby the name)

## Random walk
Random walk noise process is the integration of a white noise process

This model can represent the residual bias term well, with the exception that a true random walk is unbounded.

Noise models can thus also deploy an exponential damping term to reflect that errors in reality are not unbounded.

## Scaling factors
One unit of effect has a scaling factor error in the measurement.



