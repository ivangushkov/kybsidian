## Zero Velocity Update

Use the accelerometers to detect the magnitude and direction of total gravity vector for the gravity model at our current location.

If it is within a small tolerance range of the expected value and stays there for a predefined threshold, we declare a Zero velocity UPdaTe


Note that this observes zero relative acceleration, which is not equal to zero velocity but often coincides.


Can be treated as a "virtual measurement" when this situation is observed

	Reset growth in the system velocity error state periodically.