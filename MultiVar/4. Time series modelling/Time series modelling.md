Statistical forecasting in timeseries: We assume approximate stationarity!

This is equivalent to creating a time-invariant model in our [[Dynamical system modelling]]

If we mix modes (non-stationarity), we will end up creating a model that "averages" the modes, and will never be correct for any of them!


In many robotics application, we do not have [[Ergodicity]]! I.e. moving to an operating point

	Assuming complete ergodicity means that we weigh all past samples 
    equally. This may not be a good idea always!

If we can see past non-ergodic tendencies then using a lot of the historical data may not be a good idea.