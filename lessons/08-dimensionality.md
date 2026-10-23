# Fewer columns

## PCA

PCA draws a new first axis along the longest direction of the point cloud, then the next longest at a right angle, and so on. Those directions are the principal components. Keeping the first few drops short directions, which are often noise or repeated information.

Order of work:

1. Standardize. Center each column, and usually scale it, or a huge column steals the longest direction.
2. Compute the covariance matrix. Each cell says how two columns move together.
3. Find eigenvectors. A direction of stretch, with an eigenvalue for how much stretch.
4. Sort by eigenvalue and keep the top ones.
5. Project each point onto the kept axes.

Explained variance ratio is that eigenvalue divided by the sum of eigenvalues. If the first two add to 0.9, they carry 90% of the spread. The new columns are mixtures of the old ones, so they are harder to name.

## Neighbor-preserving maps

A later picture keeps who is near whom, not the big spreads. Distances become probabilities of being neighbors. Kullback-Leibler divergence scores how badly the low-dimensional probabilities disagree with the original ones, with extra pain when close points are torn apart.

You move the map points to shrink that cost. The picture is for looking. Cluster size and the gap between blobs are not faithful measurements. A clean separation can be the algorithm insisting on one. Rerun with different settings before you tell a story.
