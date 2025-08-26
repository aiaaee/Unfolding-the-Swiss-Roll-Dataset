# Unfolding the Swiss Roll Dataset

<img width="495" height="482" alt="image" src="https://github.com/user-attachments/assets/7cfd730a-5944-48b5-ae09-a7826208685f" />

This project explores the **Swiss Roll dataset**, a classical benchmark in machine learning used to study **clustering** and **manifold learning** methods.  
The aim is to compare traditional clustering algorithms (such as K-Means and Gaussian Mixture Models) with modern manifold learning approaches (such as Isomap, Locally Linear Embedding, MDS, and t-SNE) in order to understand their strengths and limitations.  


## Introduction 

The **Swiss Roll** dataset is a synthetic 3D dataset commonly used to test algorithms in:  
- **Clustering**  
- **Dimensionality Reduction**  
- **Manifold Learning**  

Its nonlinear, rolled-up structure makes it an excellent test case: simple clustering often fails to capture the underlying geometry, while manifold learning techniques can "unfold" the dataset into a meaningful 2D representation.  
<img width="1395" height="525" alt="newplot (23)" src="https://github.com/user-attachments/assets/8801813b-2ee8-4fd3-b48f-82612915ae78" />

---

## Methods Implemented

### 1. **K-Means Clustering**
- **Concept:** Partitions data into $k$ spherical clusters by minimizing within-cluster variance.  
- **On Swiss Roll:** K-Means assigns clusters, but fails to respect the curved manifold structure — clusters are often sliced across the roll rather than along its natural unfolding.  
<img width="1395" height="525" alt="newplot (30)" src="https://github.com/user-attachments/assets/4b97de37-48dd-47eb-a6d7-93371b9a9e37" />

### 2. **Gaussian Mixture Model (GMM)**
- **Concept:** A probabilistic model assuming data is generated from a mixture of Gaussian distributions with different means and covariances.  
- **On Swiss Roll:** Provides more flexible, elliptical clusters compared to K-Means, but still cannot fully capture the intrinsic geometry of the rolled surface.  
<img width="1395" height="525" alt="newplot (25)" src="https://github.com/user-attachments/assets/06c4cae0-a804-4e8b-9535-8397e962fc92" />

### 3. **Isomap**
- **Concept:** A nonlinear dimensionality reduction technique that preserves **geodesic distances** between points by building a neighborhood graph and applying multidimensional scaling (MDS).  
- **On Swiss Roll:** Successfully "unfolds" the dataset into a 2D plane while preserving the intrinsic geometry. One of the best-performing methods for this dataset.  
<img width="1395" height="525" alt="newplot (26)" src="https://github.com/user-attachments/assets/f17222d3-b205-4bbe-9111-94e4885eeb2d" />

### 4. **Multidimensional Scaling (MDS)**
- **Concept:** Embeds high-dimensional data into a lower-dimensional space by preserving pairwise distances as much as possible.  
- **On Swiss Roll:** MDS captures global distances but struggles with highly nonlinear manifolds, leading to distortions in the unfolding.  
<img width="1395" height="525" alt="newplot (25)" src="https://github.com/user-attachments/assets/b70196e3-b56c-43a9-954b-2f288cdc96af" />

### 5. **Locally Linear Embedding (LLE)**
- **Concept:** A nonlinear dimensionality reduction method that preserves local linear relationships among neighbors.  
- **On Swiss Roll:** Like Isomap, LLE unfolds the dataset effectively, showing strong performance in maintaining local geometry. However, it may introduce distortions near the boundaries.  
<img width="1395" height="525" alt="newplot (27)" src="https://github.com/user-attachments/assets/90b3512a-7c59-46ad-838d-6fd5e0d8fc2e" />

### 6. **t-SNE**
- **Concept:** Optimizes a probabilistic distribution of pairwise similarities in high- vs. low-dimensional space, commonly used for visualization.  
- **On Swiss Roll:** Produces a meaningful 2D embedding, but its main focus is on preserving local neighborhoods and separating clusters, not necessarily unfolding the manifold perfectly.  
<img width="1395" height="525" alt="newplot (29)" src="https://github.com/user-attachments/assets/b05bea73-d38e-48dc-bd7d-b884fca9421c" />


---


##  Results

- **Best Methods for Swiss Roll:**  
  - **Isomap** → Best at preserving the intrinsic manifold structure.  
  - **Locally Linear Embedding (LLE)** → Strong alternative with excellent unfolding capability.  

- **Clustering methods (K-Means, GMM):** Provide partitions but fail to reflect the nonlinear geometry.  
- **MDS & t-SNE:** Useful visualizations, but less effective at faithfully unfolding the roll compared to Isomap and LLE.  

---
##  Key Takeaways
- Clustering methods are limited for nonlinear manifolds like Swiss Roll.  
- Manifold learning techniques (especially **Isomap** and **LLE**) reveal the true 2D structure of the dataset.  
- This project highlights the importance of choosing algorithms aligned with the data’s geometry.  

---

##  Technologies & Libraries
- **Python 3.10+**  
- [scikit-learn](https://scikit-learn.org/)  
- [plotly](https://plotly.com/python/)  
- [numpy](https://numpy.org/)  
