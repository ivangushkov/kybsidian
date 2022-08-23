## Density Based Spatial Clustering of Applications with Noise

One of the most effective [[Clustering]] techniques

### Main idea
Define an epsilon-neighborhood (hyperparam, [[Model Order Selection]]) of a point q   so that another point p belongs to Dq if dist(p, q) < epsilon

N is the minimum number of points in the neighborhood

A "cluster" is a maximal set of density-connected points
![[Pasted image 20220721011616.png]]
This allows us to discover clusters of arbitrary shapes, since we are not only looking at the euclidean distance, but a "local distance" between points.

	Since points can be not connected to anything - these are assumed to 
    be noise!

Thus, DBSCAN employs some sort of outlier detection and rejection.

### Terms
Core points: Two points can be
	* Directly-density reachable, density-eachable, or density connected
	* The smaller epsilon, the fewer directly-density reachable
	* Increasing N increases leaf points, since we need more connections to be densely connected
Border points: A point can be on the border, i.e. only connected to one other point
Outlier: Not connected to any points

### Hyperparameters
epsilon, the maximum radius between two points in a cluster
N, the maximum amount of points in a cluster



## Algorithm

1. Arbitrarily select a point p
2. Retrieve all points density-reachable from p wrt epsilon and N
	1. If p is a core point, form a cluster
	2. If p is a border point, and no points are density reachable from p, visit the next point
3. Repeat until all points have been processed