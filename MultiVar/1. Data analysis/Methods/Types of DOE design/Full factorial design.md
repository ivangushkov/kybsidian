## Full factorial
Simplest designs for [[DoE]]
Basis for many others
Optimal for detecting main effects and their interactions

#### Approach
Define "high" and "low" for each variable. Perform runs with every combination of high and low, plus some center samples (i.e. all zero)
![[Pasted image 20220711194939.png]]

This yields 2^(amount of variables) + center samples amount of runs. Note also that we should randomize order of runs, so we dont introduce bias/hysteresis effects in the experiment itself

#### Calculations
Main effect will be the average of all variables at high minus all variables at low

For higher order effects, we extend the columns by multiplying signs from the individual effects. I.e. if A is + and B is -, then AB is -. Note that we can still only alter each component individually, but through this we can detect interaction effects