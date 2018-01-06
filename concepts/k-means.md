## K-Means Clustering

### Concept and Algorithm

K-means clustering is used to cluster data points, based on a distance (Euclidean in most cases), into k clusters that are defined initially. Each cluster has a center, called the centroid, and a data point is clustered into a certain cluster based on how close the features are to the centroid. K-means algorithm iteratively minimizes the distances between every data point and its centroid in order to find the most optimal solution for all the data points.

1. k random points of the data set are chosen to be centroids.
2. Distances between every data point and the centroids are calculated and stored.
3. Based on distance calculates, each point is assigned to the nearest cluster.
4. New cluster centroid positions are updated by taking the mean value of all of the samples assigned to each previous centroid.
5. If the centroid locations changed, the process repeats from step 2, until the calculated new center stays the same, which signals that the clusters' members and centroids are now set.

The algorithm starts off by choosing k initial centroids. Subsequently the algorithm loops between steps 2 and 3 until the centroids do not move significantly. A movement is the difference between the old and new centroid and is compared with a threshold value. The ideal result is k clusters with close to equal and least intra-cluster variance. This means that there cannot be a lower average distance between the centroids and their respective cluster points.

The objective function for the K-means clustering algorithm is the squared error function. It attempts to pick centroids that minimize the distance to all points belonging to its respective cluster.

### Additional Points

* Lloyd's algorithm is a commom k-means algorithm where k is known.
* Since distance is computed between a centroid and every data point, the algorithm becomes inefficient when trying to converge. The algorithm can be stopped after a few iterations since further iterations won’t change the assignments of the majority of data points.
* K-means performs well when the data is distinct to a large extent. Situations where it falters include overlapping data, inability to understand the underlying structure of the data, or precense of noise or outliers.
* K-means also fails to perform in high-dimensional spaces as Euclidean distances tend to become inflated (an instance of the “curse of dimensionality”). Performing dimensionality reduction (PCA) before running k-means can help speed up computations.
* K-means will converge with time but to a local minimum in many instances. Since this is highly dependent on centroid initialization, initial centroids are chosen to be distant from each other leading to a better result. This is called k-means++ and can be implimented in Python's _scikit-learn_ (use the init='k-means++' parameter).

### Sources and Readings

1. http://scikit-learn.org/stable/modules/clustering.html#k-means
2. http://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_digits.html
3. https://brilliant.org/wiki/k-means-clustering/
4. http://stanford.edu/class/ee103/visualizations/kmeans/kmeans.html
5. http://scikit-learn.org/stable/modules/clustering.html#clustering-evaluation
6. https://www.benkuhn.net/squared
