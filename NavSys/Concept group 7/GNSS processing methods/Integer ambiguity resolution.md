## Integer ambiguity resolution
Estimates of float ambiguities improve with time as geometry accumulates. I.e. the ambiguity is not usually immediatly observable, but becomes pseudo-observable over time. 
Cycle slips cause a reset in the estimation process and accuracy.

The first LS solution estimates ambiguities as real/floats, which is why the first double-difference solution is called the "float ambiguity solution".

The [[State space]] is defined to then resolve the ambiguity.

## Notes

1. It is generally easier to resolve ambiguities in static mode
2. The closer the rover is to the base station, the easier it is to resolve ambiguities (due to reduction of the correlated errors)
3. Multipath can effect the resolution process, even if the base station and rover receivers are close
4. Dual frequency receives can resolve faster than single frequency ones, by using linear combinations of the carrier phase measurements.
5. The more satellites tracked the better