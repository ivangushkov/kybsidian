## Concept
Dilution of Precision is a factor that expresses the level of degradation of the accuracy of an aspect of the navigation solution due to the geometry of the satellites.

Each measurement translates to a constraint along an axis plus a range that covers the error. Depending on the geometry between the satellites, the region of uncertainty will be different:
![[Pasted image 20220523104652.png]]

Convension: Best achievable DOP with the minimum amount of satellites (4) is DOP 1.0

DOP is only a guideline, since what we define as "good" can depend on the application.


## Calculation
Take the volume of the bounded polyhedron of the satellites, then divide by the volume of the DOP 1.0 polyhedron.
![[Pasted image 20220523104851.png]]


The types of DOP can be calculated from the observation matrix H:
![[Pasted image 20220523105609.png]]


## HDOP
Horizontal DOP: The uncertainty in North/South, East/West directions

Calculated as: $\sqrt{D_{11} + D_{22}}$


## VDOP
Vertical DOP: The uncertainty in the vertical direction

Calculated as: $\sqrt{D_{33}}$

## PDOP
Position DOP: The uncertainty of 3-dimensional positioning

Calculated as: $\sqrt{D_{11} + D_{22} + D_{33}}$
## TDOP
Time DOP: The uncertainty of time synchronization

Calculated as: $\sqrt{D_{44}}$

## GDOP
Geometric DOP: Total uncertainty, geometry and time combined.

Calculated as: $\sqrt{D_{11} + D_{22} + D_{33} + D_{44}}$

## Notes
GDOP, PDOP, TDOP work with ECEF coordinates, while HDOP and VDOP requires recalculation and local level coordinates.

Vertical uncertainty is much greater since we can only directly observe this by the overhead satellite.

Time uncertainty is often the best observed state since **all** satellites contribute to this, regardless of where they are.

Vertical error and clock error tend to be highly correlated