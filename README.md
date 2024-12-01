# imensionality-Reduction-and-Clustering-Analyzing-Synthetic-Data-with-PCA-t-SNE-K-Means-and-DBSCAN


This README provides a explanation of the tasks performed, methodologies used, and results achieved in the context of clustering, classification, and visualization. Each task is documented with clear descriptions and steps taken, including the purpose of the task and its outputs.

---

## **Table of Contents**
1. [Introduction](#introduction)
2. [Tasks Overview](#tasks-overview)
3. [Libraries Used](#libraries-used)
4. [Task Details](#task-details)
    - [Task 1: PCA Visualization](#task-1)
    - [Task 2-3: Coordinates After Dimensionality Reduction](#task-2-3)
    - [Task 4: Visual Interpretability of PCA and t-SNE](#task-4)
    - [Task 5: Classification on Transformed Data](#task-5)
    - [Task 6: Implementing K-Means Clustering](#task-6)
    - [Task 7: Comparing K-Means Results for Different Iterations](#task-7)
    - [Task 8: Elbow Method for Optimal Clusters](#task-8)
    - [Task 9-10: DBSCAN Clustering](#task-9-10)
5. [Conclusions](#conclusions)

---

## **Introduction**

This project applies clustering, classification, and dimensionality reduction techniques to visualize and analyze datasets effectively. A synthetic dataset (`noisy_blobs`) was generated for clustering purposes, and the tasks involved implementing machine learning algorithms such as **PCA**, **t-SNE**, **K-Means**, and **DBSCAN** to gain insights into the dataset's structure and behavior.

---

## **Tasks Overview**

- **Task 1:** Dimensionality reduction and visualization using PCA and t-SNE.
- **Task 2-3:** Extract and report specific coordinates for an object after applying PCA and t-SNE.
- **Task 4:** Evaluate the separability of classes using PCA and t-SNE.
- **Task 5:** Train a classifier on transformed 2D data to evaluate model performance.
- **Task 6:** Implement custom K-Means clustering and visualize results.
- **Task 7:** Compare results for different K-Means hyperparameters.
- **Task 8:** Use the Elbow Method to determine the optimal number of clusters.
- **Task 9-10:** Perform DBSCAN clustering and analyze the impact of hyperparameters.

---

## **Libraries Used**

The following libraries were utilized:
- **NumPy**: Numerical computation.
- **Matplotlib**: Visualization.
- **Seaborn**: Advanced visualization.
- **Scikit-learn**: Implementation of machine learning algorithms.
- **IPython**: Dynamic notebook output (e.g., clearing and updating visuals).

---

## **Task Details**

### **Task 1: PCA Visualization**
- **Objective:** Reduce high-dimensional data to two components using PCA and visualize the results.
- **Steps:**
  1. PCA was applied to the dataset to project it onto a 2D feature space.
  2. Scatter plots were created to visualize class distributions.
  3. Classes were color-coded for interpretability.
- **Output:** PCA successfully visualized the dataset, and some separability between classes was observed.

---

### **Task 2-3: Coordinates After Dimensionality Reduction**
- **Objective:** Extract and report the coordinates of a specific object after dimensionality reduction.
- **Steps:**
  - Coordinates of the object at index `2` were computed after PCA and t-SNE transformation.
  - Values were rounded to two decimal places for clarity.
- **Output:**
  - PCA coordinates: `[-0.03, 0.03]`
  - t-SNE coordinates: `[0.57, 12.13]`

---

### **Task 4: Visual Interpretability of PCA and t-SNE**
- **Objective:** Evaluate whether PCA and t-SNE produced visually separable clusters.
- **Steps:**
  - Visualizations from Task 1 were analyzed to determine class separability.
- **Conclusion:** t-SNE provided better visual separability than PCA.

---

### **Task 5: Classification on Transformed Data**
- **Objective:** Train a simple classifier (Random Forest) on 2D transformed data and evaluate its performance.
- **Steps:**
  - Random Forest was trained on t-SNE-transformed data.
  - Accuracy and classification reports were generated.
- **Output:**
  - Accuracy on transformed data: **0.7438**
  - Classification showed strong performance for most classes, with some variability in precision and recall.

---

### **Task 6: Implementing K-Means Clustering**
- **Objective:** Implement K-Means clustering from scratch.
- **Steps:**
  1. Created a custom class `MyKMeans` to:
     - Initialize cluster centers.
     - Assign points to the nearest cluster.
     - Update cluster centers iteratively.
  2. Visualized the clustering process at each iteration.
- **Output:** K-Means clustering converged in 2 iterations with clear cluster assignments.

---

### **Task 7: Comparing K-Means Results for Different Iterations**
- **Objective:** Analyze the effect of the `n_iters` parameter on K-Means clustering results.
- **Steps:**
  1. Ran K-Means with `n_iters=3` and `n_iters=100`.
  2. Compared cluster assignments for both cases.
  3. Calculated how many objects changed cluster labels.
- **Output:** Number of objects that changed labels: **19**

---

### **Task 8: Elbow Method for Optimal Clusters**
- **Objective:** Use the Elbow Method to find the optimal number of clusters for K-Means.
- **Steps:**
  - Iterated over `k` values from 2 to 50.
  - Calculated the sum of squared distances to centroids for each `k`.
  - Plotted the Elbow curve to identify the optimal `k`.
- **Output:** The Elbow curve suggested that the optimal number of clusters is **3**.

---

### **Task 9-10: DBSCAN Clustering**
- **Task 9 Objective:** Cluster the data using DBSCAN with `eps=0.3`.
  - DBSCAN identified **5 clusters** with **65 outliers**.
  - The object at index `2` belonged to cluster `0`.

- **Task 10 Objective:** Experiment with different `eps` and `min_samples` values for DBSCAN.
  - Analyzed the number of clusters and outliers for each setting.
  - Visualized results for combinations of hyperparameters.
- **Output:** DBSCAN demonstrated high sensitivity to `eps` and `min_samples`, with clustering performance varying significantly.

---

## **Conclusions**
- **PCA** and **t-SNE** effectively reduced dimensionality, with t-SNE providing better class separability.
- The custom **K-Means implementation** worked well and matched the expected results from standard implementations.
- The **Elbow Method** validated the optimal cluster count for K-Means as 3.
- **DBSCAN** proved versatile but required careful tuning of `eps` and `min_samples`.
- Classification on transformed data showed decent accuracy, indicating the utility of dimensionality reduction techniques in preprocessing.
