# RMSE
Fisherian approach, very common.

$\theta$: unknown and deterministic
$\hat \theta$: estimate of $\theta$, usually a random variable

	since theta is unknown, we do not have p(theta), and such we do not 
    have the [[maximum a posteriori estimation]]

Mean squared error:
Squared error committed by a **specific realization** of $\hat \theta$: $||\theta - \hat \theta||^2$ 
Squared error committed by the entire $\hat \theta$: E$[||\theta - \hat \theta||]^2$

The geometrical interpretation of this is a distance between the true theta (unknown) and the estimated theta in the codomain that the estimator maps the dataset into.

	We CANNOT directly calculate the MSE since theta is unknown. 
    However, we may estimate it.

RMSE = $\sqrt{mse}$ 
RMSE is preferred since it preserves units (mse will square all units)

# Remarks
1. Since the MSE is a function of theta, it may have excellent performance for some specific thetas, while awful performance for others.

		Performance should thus be tested across the entire space of Theta

2. The MSE is defined over the measure y1, ..., yN, but this a function of the to-be-estimated theta!

		Thus, the MSE cannot be calculated

The strategy to estimate theta from data will for example be the sample mean of all the data.

The estimator will be trained using parts of the data, while the sample mean is our approximated "ground truth" from ALL the data.