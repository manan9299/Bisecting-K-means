# Bisecting-K-means
Implementing Bisecting K-means clustering algorithm for text mining

### K - Means
1. Randomly select 2 centroids
2. Compute the cosine similarity between all the points and two centroids
3. Segregate into 2 clusters
4. Recalculate the centroids by taking the mean of clusters and repeat the above steps

### Bisecting K - means pseudo code
1. Start with all the points and apply K means with K = 2.
2. Calculate the SSE score for both clusters
3. Select the cluster with higher SSE score
4. Apply K means iteratively on the cluster selected in the above step until total number of clusters are reached.

### Evaluation Metric
- Used Calinski and Harabaz score to evaluate the clustering algorithm.
- This score is defined as the ratio between the within-cluster dispersion and the between-cluster dispersion.
- The plot for k = 3 to 21 is as follows:

### Dimensionality Reduction algorithm
- Running bisecting K means on a dense matrix of 8580 rows and ~126000 features was using a lot of resources.
- In order to reduce the number of features, I used Truncated Singular Value Decomposition (TSVD) in order to identify the - principal components from the matrix.
- I ran the TSVD for 100 to 500 components incrementing by 50 every time, and got the best evaluation score for 200 components.


References:
- https://prakhartechviz.blogspot.com/2019/06/understanding-bisecting-k-means.html [for bisecting k means]
- https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.TruncatedSVD.html [Truncated SVD]
- https://scikit-learn.org/0.19/modules/generated/sklearn.metrics.calinski_harabaz_score.html [calinski and harabaz score]
