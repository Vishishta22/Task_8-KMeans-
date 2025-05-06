# Task_8-KMeans-

# K-Means Clustering on Mall Customers Dataset

## Overview

This project performs **unsupervised clustering** on the `Mall_Customers.csv` dataset using the **K-Means algorithm**. The goal is to segment customers based on their **Annual Income** and **Spending Score**.

---

##  Dataset Used

**Filename**: `Mall_Customers.csv`  
**Features Considered**:
- `Annual Income (k$)`
- `Spending Score (1-100)`

These two features are ideal for clustering, as they help group customers by their purchasing capacity and behavior.

---

##  Task 1: Load and Visualize Dataset

- The dataset is loaded using `pandas`, and we use a **2D scatter plot** to visualize data distribution.
- Optional preprocessing: feature scaling (if needed) and selecting only numerical features for clustering.

---

##  Task 2: Fit K-Means and Assign Cluster Labels

- KMeans model is fitted using `n_clusters = 5` (identified via Elbow Method).
- Cluster labels are assigned and stored as a new column in the DataFrame.

---

##  Task 3: Elbow Method to Find Optimal K

- Used `inertia` (within-cluster sum of squares) for K values from 1 to 10.
- The "elbow" point is detected using the **`kneed`** library, showing **Optimal K = 5**.

###  Output:

Elbow Method Plot

- **Interpretation**: After K=5, the rate of decrease in inertia slows down, indicating that adding more clusters does not significantly improve the model.

---

##  Task 4: Visualize Clusters with Color-Coding

- A scatter plot of customers is created with:
  - Color-coded clusters
  - Red centroids plotted for each cluster

### Output:

K-Means Clustering

- **Interpretation**: Clearly defined customer groups based on income and spending behavior. For example:
  - Low income, low spenders
  - High income, high spenders
  - High income, low spenders, etc.

---

## Task 5: Evaluate Clustering using Silhouette Score

- **Silhouette Score**: `0.5547`  
  (Ranges from -1 to 1. Higher is better.)

- **Interpretation**:
  - Score above 0.5 indicates that the clustering is reasonably good.
  - Points are well-matched to their own cluster and well-separated from others.

---

##  Conclusion

- The KMeans model successfully segmented mall customers into 5 distinct groups.
- This can help in targeted marketing, loyalty programs, or personalized service strategies.

---

## Libraries Used

```python
pandas
matplotlib
sklearn
kneed
```
Warning related to MKL threading can be ignored or suppressed by setting:

set OMP_NUM_THREADS=2

Ensure kneed is installed via:

pip install kneed
