# Customer Segmentation - Exploratory Data Analysis (K-Means Prep)

This repository contains the initial data loading, cleaning, and exploratory data analysis (EDA) pipeline for a customer segmentation project. The analysis serves as the foundation for building a **K-Means Clustering** model to group customers based on demographic and regional patterns.

---

## 📋 Project Overview

The notebook implements an end-to-end data ingestion and exploration process using a customer profile dataset. It verifies data integrity, profiles categorical distributions, and prepares the environment for feature engineering and unsupervised machine learning.

### Key Operations Performed:
* **Remote Data Ingestion:** Fetches the dataset dynamically from a remote GitHub raw repository.
* **Environment Synchronization:** Clones and updates the local assignment workspace.
* **Data Integrity Verification:** Validates shapes, inspects missing values, checks for duplicates, and calculates skewness metrics.
* **Feature Profiling:** Explores data categories and frequencies across segments, states, and cities.

---

## 📊 Dataset Profile

The dataset consists of profile information for **793 unique customers** across 5 specific attributes:

| Column Name | Data Type | Unique Count | Description |
| :--- | :--- | :--- | :--- |
| **id** | Object / String | 793 | Unique identifier for each customer. |
| **name** | Object / String | 793 | Full name of the customer. |
| **segment** | Object / Category | 3 | Market segment (Consumer, Corporate, Home Office). |
| **state** | Object / Category | 41 | US State where the customer resides. |
| **city** | Object / Category | 252 | City where the customer resides. |

### Summary Statistics & Findings:
* **Missing Values:** 0 (The dataset is completely clean with no null fields).
* **Duplicate Rows:** 0 (Every record represents a unique individual entry).
* **Dominant Segment:** **Consumer** is the largest segment with 409 customers.
* **Geographic Density:** **California** is the most highly represented state (161 records), and **New York City** is the top city (68 records).

---

## 🛠️ Tech Stack & Dependencies

The following libraries are imported and utilized within the environment:
* **Data Manipulation:** pandas, numpy
* **Data Visualization:** seaborn, matplotlib.pyplot
* **Machine Learning & Preprocessing:** scikit-learn (KMeans, StandardScaler)
* **Model Persistence:** joblib

---

## 🚀 Getting Started & Execution

To replicate the notebook's workflow locally or in Google Colab, execute the cells in sequence:

### 1. Environment Setup & Cloning
```bash
# Clone the repository workspace
!git clone [https://github.com/tirtho2002/Assignment-6-KMeans.git](https://github.com/tirtho2002/Assignment-6-KMeans.git)

# Move into the working directory
%cd Assignment-6-KMeans

# Ensure you have the latest source changes
!git pull origin main