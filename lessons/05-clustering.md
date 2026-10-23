# Clustering

Unsupervised: there is no class column. Objects inside a group should be alike. Objects in different groups should differ. "Alike" is a distance you chose. A bad distance gives confident nonsense.

The same drawing can be two clusters or four. Clustering matches the definition you handed it.

| Idea of a cluster | Plain meaning | Method family |
|---|---|---|
| Well separated | Everyone inside is closer to insiders than to outsiders | Rare in real data |
| Center-based | Everyone is near a center | K-means |
| Contiguity | You can walk neighbor to neighbor and stay inside | Some hierarchical cuts |
| Density | A crowded region with empty space around it | DBSCAN |
| Conceptual | They share a rule, even if far apart | Not a distance trick |

Partitional clustering cuts into k groups. Hierarchical clustering builds a tree. Exclusive means one group each. Overlapping allows several. Fuzzy means a point is partly in more than one.

## K-means

Choose k. Place k centers, often at random data points. Repeat until centers stop moving.

Assign every point to the nearest center. Move each center to the mean of its points.

SSE is the sum of squared distances from points to their own centers. It drops or stays during the two steps, and it can stop in a bad valley. Run many random starts and keep the lowest SSE.

Example. Points 1, 2, 10, 11. k = 2. Centers start at 1 and 10. Assign 1 and 2 together, 10 and 11 together. New centers are 1.5 and 10.5. Nothing moves. SSE is 1.

Plot SSE against k. The elbow, where the drop flattens, is a candidate k. Also ask whether a person can name the groups.

An empty cluster can be repaired by moving that center onto the farthest point. Bisecting k-means grows groups by repeatedly cutting one cluster in two.

K-means wants blobs of similar size and density, roughly round in your distance. A long crescent gets sliced. One fix is many small round clusters, then glue the ones that form the crescent.

## Hierarchical

Agglomerative clustering starts with each point alone and merges the closest groups until one remains. The tree is a dendrogram. Cut it to get a flat clustering. You do not pick k first. A full distance matrix is expensive.

Single linkage uses the closest pair between groups and can chain across a thin bridge. Complete linkage uses the farthest pair and prefers compact groups. Average linkage uses the mean of cross pairs.

## DBSCAN

Pick a radius and a minimum neighbor count. A core point has enough neighbors inside the radius. A border point sits in a core's radius but is not crowded. Noise is neither. A cluster is core points that can reach each other, plus their border points.

This keeps crescents and ignores loners. One radius fails when dense and sparse regions need different radii.

**Check.** Two tight round groups and one long crescent. Which method cuts the crescent, and which keeps it if the empty space around it is wide?
