# 🧠 K-Means Clustering – Customer Segmentation Project

## 📌 Project Overview
This project applies **K-Means Clustering** to a standard dataset to segment customers based on their purchasing behavior[cite: 2, 3]. The model uses **Annual Income** and **Spending Score** as features to group customers into meaningful clusters[cite: 3]. 

To demonstrate practical usage and real-world testing, the trained model pipeline is then used to predict clusters for a custom dataset of 10 real-world individuals[cite: 2, 3].

---

## 📁 Repository Structure
*   `notebook.ipynb` — Full Google Colab notebook demonstrating the entire clustering workflow[cite: 2, 3].
*   `datasets/customers.csv` — The standard training dataset[cite: 2].
*   `datasets/custom_data.csv` — Custom survey records of 10 real-world individuals[cite: 2, 3].
*   `model/kmeans_model.joblib` — The saved, trained K-Means model object[cite: 2, 3].
*   `README.md` — This file, containing project details, visual descriptions, and cluster interpretations[cite: 2].

---

## 📂 Dataset Details

### Standard Training Dataset (customers.csv)
*   **Source:** Automatically pulled directly from this GitHub repository during notebook runtime[cite: 2].
*   **Features used for clustering:**
    *   Annual Income[cite: 2, 3]
    *   Spending Score (1-100)[cite: 2, 3]

### Custom Dataset (custom_data.csv)
*   **Purpose:** Real-world prediction demonstration[cite: 2, 3].
*   **Creation:** 10 distinct data points collected from the real world, containing estimated annual income and a self-rated spending score[cite: 2].
*   **Formatting:** Processed to match the training data format exactly (identical column names and data types)[cite: 2].

---

## 🧪 Machine Learning Pipeline (Step-by-Step)

1.  **Data Loading Automation**
    *   The Google Colab notebook uses `!git clone` to download `customers.csv` and the custom data automatically, requiring no manual file uploads[cite: 2].
2.  **Data Preprocessing & Scaling**
    *   `StandardScaler` from `sklearn.preprocessing` is fitted on the selected features[cite: 2, 3]. 
    *   Because K-Means relies heavily on Euclidean distance, standardizing the data prevents distance-based penalties[cite: 2].
3.  **Optimal K Selection (Elbow Method)**
    *   The model iterates through varying numbers of clusters, computing the Within-Cluster Sum of Squares (WCSS)[cite: 2, 3]. 
    *   Based on the elbow point, the optimal $K$ is chosen as **5**[cite: 3].
4.  **Model Fitting & Saving**
    *   The KMeans model is initialized and fitted to the scaled standard dataset[cite: 2, 3].
    *   The trained model is exported and saved into the repository using `joblib`[cite: 2, 3].
5.  **Real-World Testing & Prediction**
    *   The custom dataset is loaded via `pandas` and scaled using the **exact same fitted scaler** applied to the standard dataset[cite: 2].
    *   The pipeline uses `model.predict()` to assign the newly surveyed individuals to the established clusters[cite: 2].

---

## 📊 Visualizations & Output

### 1. The Elbow Curve Plot
A line graph plotting the Number of Clusters ($K$) on the X-axis against the WCSS on the Y-axis[cite: 2]. This training loss-like curve visually justifies the selection of 5 clusters[cite: 3].

### 2. Cluster Scatter Plot
A 2D scatter plot of the scaled standard dataset that colors the distinct clusters and marks the final calculated centroids with a distinct **X** symbol[cite: 2, 3].

### 3. Custom Prediction Output
A formatted DataFrame table displaying the 10 custom survey items alongside their newly assigned Cluster IDs[cite: 2, 3].

---

## 🧠 Cluster Interpretation

Based on the final centroid placements, the 5 distinct clusters represent the following customer profiles:

*   **Cluster 0:** High income + high spending (premium customers)[cite: 3].
*   **Cluster 1:** High income + low spending (cautious wealthy customers)[cite: 3].
*   **Cluster 2:** Low income + high spending (impulsive buyers)[cite: 3].
*   **Cluster 3:** Low income + low spending (budget-conscious customers)[cite: 3].
*   **Cluster 4:** Average income + average spending (regular customers)[cite: 3].