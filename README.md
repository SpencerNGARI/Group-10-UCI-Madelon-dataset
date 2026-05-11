# Group 10 — UCI Madelon Dataset: Clustering Analysis

## Overview
This project applies unsupervised machine learning to the UCI Madelon dataset,
a high-dimensional binary classification dataset with 500 features, of which
only 20 are informative and 480 are pure noise by design. Our goal is to
compare three clustering algorithms — K-Means, Hierarchical (Agglomerative),
and DBSCAN — and evaluate their ability to recover meaningful structure from
this intentionally challenging dataset.

**Course:** Data Science and Analytics
**Institution:** Jomo Kenyatta University of Agriculture and Technology (JKUAT)
**Repository:** https://github.com/SpencerNGARI/Group-10-UCI-Madelon-dataset

---

## Dataset
| Property | Value |
|----------|-------|
| Name | UCI Madelon Dataset |
| Samples | 2,600 (2,000 train + 600 validation) |
| Features | 500 numeric features |
| Informative features | 20 |
| Noise features | 480 |
| Ground truth labels | Binary: +1 / -1 |

The dataset was provided by link from the course lecturer.

---

## Pipeline
```
Raw Data → EDA → Preprocessing → PCA → K-Means
                                     → Hierarchical
                                     → DBSCAN
                                          → Evaluation & Report
```

PCA is applied before clustering to reduce 500 features to 50 components
for clustering and 2 components for visualisation. This step is essential
given the high proportion of noise features.

---

## Notebooks
| # | Notebook | Description |
|---|----------|-------------|
| 01 | 01_data_loading.ipynb | Load and combine train/validation sets |
| 02 | 02_eda.ipynb | Distributions, variance, correlation heatmap |
| 03 | 03_preprocessing.ipynb | StandardScaler feature scaling |
| 04 | 04_pca.ipynb | PCA dimensionality reduction (500 → 50) |
| 05 | 05_kmeans.ipynb | K-Means clustering + elbow + silhouette |
| 06 | 06_hierarchical.ipynb | Agglomerative clustering + dendrogram |
| 07 | 07_dbscan.ipynb | DBSCAN + KNN distance tuning |
| 08 | 08_evaluation.ipynb | Metrics comparison + final summary |

---

## Algorithms
| Algorithm | Key Parameters | Notebook |
|-----------|---------------|----------|
| K-Means | k (elbow method + silhouette) | 05_kmeans.ipynb |
| Hierarchical | linkage (Ward/Complete/Average) | 06_hierarchical.ipynb |
| DBSCAN | eps (KNN distance graph), min_samples | 07_dbscan.ipynb |

---

## Evaluation Metrics
| Metric | Measures | Best Value |
|--------|----------|------------|
| Silhouette Score | Cluster separation (internal) | Closer to 1 |
| Davies-Bouldin Index | Within vs between cluster distance | Closer to 0 |
| Calinski-Harabasz Score | Between vs within cluster variance | Higher |
| Adjusted Rand Index | Agreement with ground truth | Closer to 1 |
| Normalised Mutual Info | Shared info with ground truth | Closer to 1 |

---

## Setup

### 1. Clone the repository
```bash
git clone https://github.com/SpencerNGARI/Group-10-UCI-Madelon-dataset.git
cd Group-10-UCI-Madelon-dataset
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run notebooks in order
Start from `01_data_loading.ipynb` and run sequentially.
Notebooks 05, 06, and 07 depend on the PCA output from notebook 04.

---

## Repository Structure
```
Group-10-UCI-Madelon-dataset/
├── data/
│   ├── raw/                  # Original dataset files
│   └── processed/            # Scaled and PCA-transformed data
├── notebooks/                # Jupyter notebooks (01–08)
├── src/                      # Reusable Python modules
├── outputs/
│   ├── figures/              # All saved plots
│   └── models/               # Saved model objects
├── report/                   # Final written report
├── requirements.txt
└── README.md
```

---

## Branch Workflow
Each member worked on a dedicated `dev/` branch and submitted work
via Pull Request to `main`. Direct pushes to `main` were disabled.

| Branch | Responsibility |
|--------|---------------|
| main | PM / GitHub Coordinator |
| dev/data-loading | Dataset loading |
| dev/eda | Exploratory data analysis |
| dev/preprocessing | Feature scaling and preprocessing |
| dev/pca | PCA dimensionality reduction |
| dev/kmeans | K-Means clustering |
| dev/hierarchical | Hierarchical clustering |
| dev/dbscan | DBSCAN clustering |
| dev/evaluation-report | Evaluation and final report |

---

