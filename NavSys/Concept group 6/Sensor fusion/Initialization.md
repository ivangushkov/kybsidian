Intialization requires state information, ideally [[PVT]]

To initialize an integrated navigation system, the best way is to directly measure states where possible.


1. Position initialization can come from the GNSS receiver directly
2. GNSS velocity however is not necessarily a good idea: If you lie to the [[Kalman Filter]] it will happily lie back 

For velocity then, option 1 is to inflate the variance estimates of the velocity measurements before using them during initialization.

Option 2 is to use the accelerometer outputs to detect a special state call [[ZUPT]]


This can be robustified by [[ZARU]]

3. Roll and pitch can be coarse alligned using acceleration measurements (relating to gravity!)
4. Yaw is not observable using gravity alone. We can however pseudo-observe the yaw using roll and pitch knowing where we are on earth, given earth rotation. Additionally point the system facing a known yaw (i.e. North.). Dynamic option can be done by moving the platform in a straight direction forwards, thus pseudo-observing coarse. 


## Pull-in
A manifold about the true state in which if we initialize, the [[Kalman Filter]] will converge to the true solution. Otherwise it may diverge.