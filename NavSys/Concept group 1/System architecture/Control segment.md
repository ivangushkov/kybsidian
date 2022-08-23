Feedback loop with [[Space segment]]

Many ground stations around the world. Yields good coverage to turn off broken satellites etc.

Control segment has a section for sending updated data to the satellites.

## Error correction
Satellite clock drift compensation. see [[Clock accuracy]]

#### For the satellite
Orbits of the satellites change over time. Gravity model is kept by the control segment to counteract changes.
Satellites broadcast own orbits for an idealized two body system. Since this is not actually true, it is corrected for.
Solar radiation pressure causes the satellite to be pushed. But the satellite needs maximum surface towards the sun for their solar panels

Models the earth as an ellipse in accordance with [[WGS84]]

**Ranging error is entirely correlated with clock error!!!**: One solution: corner cube corrector to measure range. Laser is sent from control segment to get a ranging measurement


#### For the control segments
Control segments drifts relative to one another (cm per year). Needs to be taken into account!

Glacial rebound, earth rises slowly after ice 


## Data upload
Batches of 24 hours due to historical measurement: That means that the satellite is predicting bias and errors up to 24 hours into the future!

Two parts: [[Almanac]] and the [[Ephemeris]]


## Robustness
If all control segments are knocked out, the satellites will intercommunicate.

Clock error is reduced by utilizing the ensemble of clocks in all sats
Orbital error is slowed by measuring ranges and range rate between sats

16m for users out to 60 days!