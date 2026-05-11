# Group-10-UCI-Madelon-dataset
Project applying unsupervised learning to UCI Madelon dataset
Density‑Based Spatial Clustering of Applications with Noise (DBSCAN) for our dataset. DBSCAN is chosen because it can discover clusters of arbitrary shape and identify noise/outliers without requiring the number of clusters in advance.

Why PCA? 500 features is a lot. Many are redundant (MADELON has 480 noise features by design!). PCA finds the directions of maximum variance and compresses the data into fewer, more meaningful components.

We use PCA for two purposes:

Clustering: Reduce to 50 components (capturing most variance) before running algorithms
Visualisation: Reduce to 2 components to plot clusters

# Responsibilities 
eps tuning: Determined using the k‑distance graph to find the "elbow point."

min_samples tuning: Adjusted based on dataset dimensionality and density.

Noise detection analysis: Evaluated points labeled -1 to distinguish anomalies from data quality issues.

# Deliverables
DBSCAN implementation (dbscan.py) with reproducible code.

k‑distance plot (results/k_distance_plot.png) to justify parameter selection.

Noise cluster analysis (results/noise_analysis.md) documenting percentage and nature of outliers.

# Limitations
DBSCAN may struggle in high‑dimensional datasets due to the curse of dimensionality, where distance metrics lose meaning.
