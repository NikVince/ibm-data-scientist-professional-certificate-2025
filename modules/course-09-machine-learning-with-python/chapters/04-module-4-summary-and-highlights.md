# Course 9, Module 4: Summary and Highlights

## Overview
This module introduces clustering and dimensionality reduction. You learned k-means and its evaluation heuristics, density-based methods (DBSCAN/HDBSCAN), hierarchical clustering, and how PCA, t-SNE, and UMAP reduce dimensionality for better modeling and visualization.

## Clustering Techniques
- Clustering groups data by similarity; common use cases include customer segmentation and anomaly detection.
- K-means partitions data into k clusters using distances to centroids; can struggle with imbalanced or non-convex clusters.
- Heuristics for selecting k and assessing fit: silhouette score, elbow method, Davies–Bouldin Index.
- DBSCAN forms clusters based on density; effective for natural, irregular shapes.
- HDBSCAN extends DBSCAN, leveraging cluster stability and reducing parameter sensitivity.
- Hierarchical clustering (divisive top-down or agglomerative bottom-up) yields a dendrogram to visualize hierarchy.

## Dimensionality Reduction
- Reduces noise and simplifies structure, often improving clustering and feature selection.
- PCA (linear) minimizes information loss while reducing dimensionality and noise.
- t-SNE and UMAP map high-dimensional data into lower dimensions for visualization and analysis.
- Example applications include face recognition (eigenfaces).

## Takeaways
- Choose clustering based on data shape, scale, and density patterns.
- Use silhouette/elbow/Davies–Bouldin to assess k-means; prefer DBSCAN/HDBSCAN for irregular clusters.
- Combine dimensionality reduction (PCA/t-SNE/UMAP) with clustering to enhance separation and interpretability.

