# Unfolding the Swiss Roll Dataset
<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/02bb7b22-6942-47a6-90d9-062e07226e27" />

This project explores the **Swiss Roll dataset**, a classical benchmark in machine learning used to study **clustering** and **manifold learning** methods.  
The aim is to compare traditional clustering algorithms (such as K-Means and Gaussian Mixture Models) with modern manifold learning approaches (such as Isomap, Locally Linear Embedding, MDS, and t-SNE) in order to understand their strengths and limitations.  


## Introduction 

The **Swiss Roll** dataset is a synthetic 3D dataset commonly used to test algorithms in:  
- **Clustering**  
- **Dimensionality Reduction**  
- **Manifold Learning**  

Its nonlinear, rolled-up structure makes it an excellent test case: simple clustering often fails to capture the underlying geometry, while manifold learning techniques can "unfold" the dataset into a meaningful 2D representation.  

---

## Methods Implemented

### 1. **K-Means Clustering**
- **Concept:** Partitions data into $k$ spherical clusters by minimizing within-cluster variance.  
- **On Swiss Roll:** K-Means assigns clusters, but fails to respect the curved manifold structure — clusters are often sliced across the roll rather than along its natural unfolding.  

### 2. **Gaussian Mixture Model (GMM)**
- **Concept:** A probabilistic model assuming data is generated from a mixture of Gaussian distributions with different means and covariances.  
- **On Swiss Roll:** Provides more flexible, elliptical clusters compared to K-Means, but still cannot fully capture the intrinsic geometry of the rolled surface.  

### 3. **Isomap**
- **Concept:** A nonlinear dimensionality reduction technique that preserves **geodesic distances** between points by building a neighborhood graph and applying multidimensional scaling (MDS).  
- **On Swiss Roll:** Successfully "unfolds" the dataset into a 2D plane while preserving the intrinsic geometry. One of the best-performing methods for this dataset.  

### 4. **Multidimensional Scaling (MDS)**
- **Concept:** Embeds high-dimensional data into a lower-dimensional space by preserving pairwise distances as much as possible.  
- **On Swiss Roll:** MDS captures global distances but struggles with highly nonlinear manifolds, leading to distortions in the unfolding.  

### 5. **Locally Linear Embedding (LLE)**
- **Concept:** A nonlinear dimensionality reduction method that preserves local linear relationships among neighbors.  
- **On Swiss Roll:** Like Isomap, LLE unfolds the dataset effectively, showing strong performance in maintaining local geometry. However, it may introduce distortions near the boundaries.  

### 6. **t-SNE**
- **Concept:** Optimizes a probabilistic distribution of pairwise similarities in high- vs. low-dimensional space, commonly used for visualization.  
- **On Swiss Roll:** Produces a meaningful 2D embedding, but its main focus is on preserving local neighborhoods and separating clusters, not necessarily unfolding the manifold perfectly.  

---
