## Definition 

A unit vector pointing towards the object. Notated as $n_{r, o}^{f}$ where r is the reference, o is the object and f is the frame we resolve in.


## Examples


#### Travel from b to c
Using e (earth) as resolving frame.

1. form $n_{eb}^e$ and $n_{ec}^e$ 
2. form a vector from b to c as $\Delta n_{cb}^e$
3. optionally use a rotation matrix to take the vector from e to some other frame

#### Recover latitude and longitude from an n vector
![[Pasted image 20220520165239.png]]

#### Find where two courses cross
Utilize that the n vectors for each corse is orthonormal at the intersection. Calculate the cross product between the source and destination vectors along each trajectory.

Trajectory 1: A to B
Trajectory 2: C to D

point of intersection has the nvector nC-nD cross nA-nB