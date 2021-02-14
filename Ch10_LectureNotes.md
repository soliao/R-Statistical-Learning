# Ch.10 Unsupervised Learning

---

### PCA & Clustering

- PCA finds a low-dimensional representation to capture the majority of the variance in the data

- Clustering finds homogeneous subgroups among the data
    - K-means
        - pre-select K
        - should run the algorithm multiple times because K-means only finds the **local optimum**
    - Hierarchical clustering
        - the height of the cut determines the number of clusters
        - similarity between clusters is determined by the height where the 2 branches fuse on the vertical axis
            - higher: less similar
            - lower: more similar
        - hierarchical clustering may be worse than K-means if the the data lack a hierarchical structure
    - **dissimilarity** meausres
        - Euclidean distance
        - correlation-based
    - **linkage** defines the dissimilarity between two groups of observation
        - complete: maximum dissimilarity between the groups
        - single: minimum dissimilarity
        - average: average dissimilarity
        - centroid: dissimilarity between the centroids of the two groups. This method may lead to *inversion*
