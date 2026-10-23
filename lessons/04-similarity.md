# How alike are two things?

Clustering and k-nearest neighbors are this idea, repeated.

Minkowski distance is the family that contains Euclidean and Manhattan. Raise each absolute difference to power r, add, then take the r-th root. r = 2 is Euclidean. r = 1 is Manhattan. Large r cares mostly about the single biggest difference.

A proper distance obeys: distance to yourself is 0, distance is never negative, A to B equals B to A, and a straight trip is never longer than a detour.

Mahalanobis distance stretches the ruler so a step along a direction where data already varies a lot counts as smaller. Use it when columns are correlated and have different spreads.

For yes/no attributes, simple matching counts shared yes and shared no. Jaccard ignores shared no. If two shoppers both skipped 9,000 products, those shared nos are not friendship. Jaccard is shared purchases over the union of purchases.

Cosine similarity compares direction of word-weight lists. Two articles on the same topic score high even if one is much longer.

Pearson correlation measures a straight-line relationship, from -1 to 1. A perfect curve can still have correlation near 0. x = -3, -2, -1, 0, 1, 2, 3 and y = x squared is the classic case. Look at the scatter plot.
