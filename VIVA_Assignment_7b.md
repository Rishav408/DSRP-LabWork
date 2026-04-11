# VIVA Study Guide: Assignment 7b
## Topic: K-Means Clustering

### 1. Objective
To partition an unlabeled dataset (unsupervised learning) into $K$ distinct, non-overlapping groups (clusters) where items in a cluster are as similar as possible.

### 2. Theoretical Concepts
*   **Euclidean Distance:** The default metric used to measure the distance between a data point and a cluster center.
*   **Centroid:** The geometric center of a cluster (calculated as the mean of all points in the cluster).
*   **The Algorithm Process:**
    1.  Pick $K$ random centroids.
    2.  Assign each data point to the nearest centroid.
    3.  Recalculate centroids based on assignments.
    4.  Repeat until the centroids no longer move (convergence).
*   **Determining Optimal $K$:**
    *   **Elbow Method:** Plot Total Within-Cluster Sum of Squares (WSS) against $K$. The "elbow" point (where WSS drop slows down) is the optimal $K$.
    *   **Silhouette Method:** Measures how well a point matches its own cluster compared to others. A higher average silhouette width is better.

### 3. Coding Workflow in R
1.  **Library:** `library(cluster)` and `library(factoextra)`.
2.  **Preprocessing:**
    *   **Scaling:** `scaled_data <- scale(iris[, 1:4])`. Scaling is mandatory because K-Means is distance-based.
3.  **Optimal $K$ Check:**
    *   `fviz_nbclust(scaled_data, kmeans, method = "wss")` (Elbow).
    *   `fviz_nbclust(scaled_data, kmeans, method = "silhouette")` (Silhouette).
4.  **Model Training:**
    *   `km_out <- kmeans(scaled_data, centers = 3, nstart = 20)`
    *   `nstart = 20` means the algorithm will try 20 different random starting positions and pick the one with the lowest total WSS.
5.  **Visualization:**
    *   `fviz_cluster(km_out, data = scaled_data)`: Plots clusters on the principal components (PCA).

### 4. Key Metrics
*   **Between_SS / Total_SS:** High ratio (e.g., > 80%) indicates good separation between clusters.
*   **Total_Within_SS:** Lower is better (more compact clusters).

### 5. Potential VIVA Questions
*   **Q: Why do we normalize or scale data before K-Means?**
    *   A: If one feature has a much larger range (e.g., Salary vs. Age), the distance calculation will be dominated by that feature. Scaling ensures all features contribute equally.
*   **Q: Is K-Means sensitive to outliers?**
    *   A: Yes, since the centroid is calculated as a mean, extreme outliers can pull the centroid away from the true center.
*   **Q: What is the main difference between K-Means and Classification?**
    *   A: K-Means is **unsupervised** (we don't know the labels beforehand). Classification is **supervised** (we train on known labels).
