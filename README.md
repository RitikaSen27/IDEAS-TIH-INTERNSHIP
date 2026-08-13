# Breast Cancer Clustering & Dimensionality Reduction

Unsupervised learning project analyzing the Breast Cancer Wisconsin dataset using PCA, t-SNE, and UMAP for dimensionality reduction, combined with KMeans, DBSCAN, and Gaussian Mixture Models for clustering.

## Project Overview
- **Dataset:** sklearn's Breast Cancer Wisconsin dataset (569 samples, 30 features)
- **Dimensionality reduction:** PCA, t-SNE, UMAP compared side by side
- **Clustering methods:** KMeans, DBSCAN (with per-embedding eps tuning via k-distance graphs), Gaussian Mixture Models
- **Evaluation:** Silhouette score, Adjusted Rand Index (ARI), Normalized Mutual Information (NMI) against true diagnosis labels

## Key Findings
- 2D PCA retains only ~63% of variance (not ~95% as commonly assumed) — 10 components are needed to reach 95%
- Non-linear reduction (UMAP, t-SNE) outperforms PCA on every clustering metric
- DBSCAN requires per-embedding `eps` tuning — a fixed `eps` across PCA/t-SNE/UMAP unfairly penalizes it, since each embedding operates at a different distance scale
- Even after tuning, DBSCAN's behavior differs qualitatively by embedding: it collapses to one dominant cluster on PCA, finds a near-binary split on t-SNE, and reveals finer 7-way substructure on UMAP

## Results

**Clustering performance across dimensionality reduction methods** (evaluated against true diagnosis labels):

| Method | Reduction | Silhouette | ARI | NMI | Clusters found |
|---|---|---|---|---|---|
| KMeans | PCA | 0.508 | 0.659 | 0.540 | 2 |
| GMM | PCA | 0.474 | 0.655 | 0.536 | 2 |
| KMeans | t-SNE | 0.531 | 0.690 | 0.586 | 2 |
| GMM | t-SNE | 0.530 | 0.737 | 0.624 | 2 |
| **KMeans** | **UMAP** | **0.577** | **0.773** | **0.688** | 2 |
| GMM | UMAP | 0.577 | 0.767 | 0.688 | 2 |

**DBSCAN: before vs. after per-embedding eps tuning:**

| Embedding | eps (untuned) | ARI (untuned) | eps (tuned, via k-distance) | ARI (tuned) | Clusters (tuned) |
|---|---|---|---|---|---|
| PCA | 0.5 | 0.464 | ~1.1 | 0.070 | 2 (521/5 split — imbalanced) |
| t-SNE | 0.5 | 0.000 | ~2.7 | 0.705 | 4 (179/370 split — near-binary) |
| UMAP | 0.5 | 0.002 | ~0.33 | 0.464 | 7 (fine substructure) |

## Files
- `Breast_cancer_clustering_project.ipynb` — original clustering pipeline
- `10_unsupervised_learning_with_dimensionality_reduction.ipynb` — extended analysis (t-SNE, UMAP, DBSCAN tuning, comparative evaluation)
- `Breast_Cancer_Clustering_Project_Report.pdf` — internship report

## Tech Stack
Python, scikit-learn, UMAP, Matplotlib, Seaborn, Pandas, NumPy

