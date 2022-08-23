One of the simplest ones!

Performs well on simple, distinct clusters. Does not perform well on more "ill-behaved clusters"


K = K amount of clusters, decided a priori. This is the order of our model, thus a [[Model Order Selection]] problem arises


## Workflow
1. Specify K
2. Initialize centroids by shuffling and selecting without replacement.
3. Compute the sum of the squared distance between the data points and all centroids
4. Assign each data point to the closest centroid
5. Recompute the position of the various centroids by averaging the points that belong to each cluster
6. Go to 3 unless the clusters have "settled"



## Notes
Since "similarity" means "distance", we need to normalize the data first

Different initializations may lead to potentially different clusterings stuck on local optimum. Better to launch different runs starting from different initial conditions.


## Selecting K
Suggested strategy is the "elbow method". I.e. choose the k where the sum of squared errors starts flattening out. If the data is not clear, this will not always give a clear answer.


## Notes
More weight is given to bigger clusters
Implicitly assumes spherical clusters due to the sum of squares, thus different shapes may not work well
Overlapping clusters may destroy the results