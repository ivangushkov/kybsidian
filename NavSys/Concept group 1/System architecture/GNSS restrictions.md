## GNSS restrictions 

1. The satellites are in medium earth orbit
2. The power budget of the satellite is very limited
3. The signals should pass through the [[Ionosphere]] with minimal distortion
4. The signals should have some level of jamming resistance
5. The user on the ground must be able to find the signals
6. The users on the ground must be able to distinguish between satellites


These are in part tackled by the [[GNSS problems]], but the problems associated with the restrictions are outlined below, as well as some solutions.


## 0 and 1
Can be solved with [[Coherent integration]] and non-[[Coherent integration]] which exploits the fact that thermal noise is (ideally) uncorrelated white noise.

	Boost SNR by "adding up more of the signal" i.e. white noise 
    decorrelation and signal accumulation

## 2
Distance error caused by the [[Ionosphere]] is a constant divided by the square of the signal frequency, meaning that higher frequency is better! See also **4** in [[GNSS problems]].

## 3


## 4, 5 and 6
The spreading nature of [[DSSS]] means that when we unspread the signal in the [[User segment]] we also spread out narrowband frequencies by the same amount. 

See [[Signal recovery]] and [[Signal alignment]] for further details.




