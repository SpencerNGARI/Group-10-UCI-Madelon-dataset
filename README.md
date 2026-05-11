# Group-10-UCI-Madelon-dataset
Why PCA? 500 features is a lot. Many are redundant (MADELON has 480 noise features by design!). PCA finds the directions of maximum variance and compresses the data into fewer, more meaningful components.

We use PCA for two purposes:

Clustering: Reduce to 50 components (capturing most variance) before running algorithms
Visualisation: Reduce to 2 components to plot clusters
