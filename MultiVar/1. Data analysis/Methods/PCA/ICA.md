## The problem

Extract pure sources from a set of mixed sources. That is, recover clean sources from sensor observations with noise where the noise and signals are assumed uncorrelated.

Mixed images and speech/sound separation as examples:
* Two images can be overlayed. The full image is then a mix of two independent sources
* Speech recognition, where voices are embedded in noise

		Need at least as many sensor observations as sources

It is common to employ [[PCA]] before ICA, and rotating the data in the direction of the PCs and scaling to unit variance

PCA loadings can be a starting point: Then ICA can be seen as an oblique rotation method (i.e. not restricted to orthogonality).

Since we are estimating independency, we can also use ICA as a classifier


[[Cross validation]] is not straight forward in ICA due to ambiguity in many algorithmnic implementation. It is also not possible to sequentially estimate each IC without the previous one potentially changing.

	The order of the components is arbitrary, which must be accounted 
    for when applying cross validation!

See paper from Frank about this!

## Signal examples
![[Pasted image 20220714175008.png]]


## Geometry
We can see that there are two linear and independent models at play, and so for this situation, ICA gives a better result than [[PCA]]
![[Pasted image 20220714172947.png]]


## Mathematics
Two variables are uncorrelated if their covariance is zero
Two signals are stastistically independent with dist P(s1, s2) = P(s1)P(s2)

![[Pasted image 20220714174349.png]]

We wish to find s, and so our goal is to estimate A s.t. we can find s as A^-1 x

A inverse is usually called W, s.t. s = Wx

## Gaussians
		No more than one of the source signals can follow a gaussian 
        distrubution

The problem with gaussians is that a linear transformation of a gaussian is itself a gaussian. Thus, if x has gaussians, Wx will be a gaussian no matter what W we choose.

Since the scaling of each IC, is unknown, we can fix this to f.ex 1.
Then, the only gaussian with independent coordinate is the univariate gaussian.

All other gaussian reduce to this case! We can then at most have one source that is gaussian.

## Objective functions for estimating ICA
Multiple methods



