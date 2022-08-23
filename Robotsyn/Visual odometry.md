## Overview

Compute pose of camera by concatenating all rigid body transforms

Uncertainty propagates to combined covariance. 

Uncertainty always increases when concatenating transformations!

Pose-graph optimization to minimize the uncertainty - Also for non-adjacent frames!
Bundle adjustment adds optimization to 3D points.

Bundle adjustment is more precise but also more costly

Non adjacent frames add more constraints.

## Accuracy evaluation
Not trivial

End-pose error is not good! Most VO non deterministic and too sensitive

#### Absolute trajectory error
RMSE for each point in trajectory, NEED GROUND TRUTH and many points, but yields a single metric

#### Relative trajectory error
Error for all subsets of certain length. Yields a distribution (normal most likely?)


## Drift
Drift by accumulating errors in concatenating transformation
Drift can be cancelled by [[Loop closures]]




