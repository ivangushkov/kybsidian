## Euler angles

x is "forwards", y is "right" and z is "down" - NED
roll pitch yaw is respective right hand rotation in x y z. These are euler angles

These have a singularity at the poles.


## Quaternion

More computationally effective than rotation matrices (DCM) but less intuitive.


## Rotation transformation
A rotation matrix $R_b^a$ takes a value in frame b to frame a. This can be defined from the matrix product of rotation matrices about each of the three axis

Rotations can cascaded by multiplying matrices.


## Kinematic notation

$X_{ba}^c$   : a is the object frame and is the frame whos motion is described. b is the reference frame in which the motion is in relation to. c is the frame in which the motion is represented/resolved in.


## Rotation rate 
Rotation rate is a vector of rotation rates of the body frame, w.r.t. the inertial frame, resolved in the body frame.
![[Pasted image 20220528161245.png]]

Rotation rate matrix, i.e. instead of rotation rate vector (similar to rpy vs DCM)
![[Pasted image 20220528161153.png]]
![[Pasted image 20220528161159.png]]