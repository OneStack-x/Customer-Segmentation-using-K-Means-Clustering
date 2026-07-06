# Customer Segmentation using K-Means Clustering

## Overview

This project applies **K-Means Clustering** to segment customers based on their purchasing behavior using the **Online Retail II** dataset.

Instead of predicting a target variable, this project groups customers with similar shopping patterns using **RFM (Recency, Frequency, Monetary) Analysis**.

The resulting customer segments can help businesses better understand customer behavior and support marketing strategies.

---

## Dataset

**Dataset:** Online Retail II

The dataset contains over **1 million retail transactions** from a UK-based online retailer.

### Features

- Invoice
- StockCode
- Description
- Quantity
- InvoiceDate
- Price
- Customer ID
- Country

---

## Project Workflow

### 1. Data Loading

- Loaded the dataset
- Explored the dataset structure

### 2. Data Cleaning

- Removed rows with missing Customer IDs
- Removed rows with missing product descriptions
- Removed cancelled invoices
- Removed transactions with non-positive quantities
- Removed products with non-positive prices
- Converted `InvoiceDate` to datetime format

### 3. Feature Engineering

Created a new feature:

- **TotalAmount = Quantity × Price**

Built an **RFM table** where each customer is represented by:

- **Recency** – Days since the last purchase
- **Frequency** – Number of unique invoices
- **Monetary** – Total amount spent

### 4. Data Preprocessing

- Standardized the RFM features using **StandardScaler**

### 5. Customer Clustering

- Used the **Elbow Method** to determine the optimal number of clusters
- Trained a **K-Means** clustering model
- Assigned each customer to a cluster

### 6. Cluster Analysis

- Calculated the average Recency, Frequency, and Monetary values for each cluster
- Visualized customer clusters
- Evaluated clustering quality using the **Silhouette Score**

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn

---

## Machine Learning Pipeline

```
Online Retail Transactions
            │
            ▼
      Data Cleaning
            │
            ▼
  Feature Engineering
 (Create TotalAmount)
            │
            ▼
      Build RFM Table
            │
            ▼
     StandardScaler
            │
            ▼
      Elbow Method
            │
            ▼
     K-Means Clustering
            │
            ▼
   Customer Segmentation
            │
            ▼
 Cluster Interpretation
```

---

## Model Evaluation

The clustering model was evaluated using:

- Elbow Method
- Silhouette Score

---

## Repository Structure

```
customer-segmentation-kmeans/
│
├── customer_segmentation_kmeans.ipynb
└── README.md
```

---

## Future Improvements

- Perform outlier detection before clustering
- Compare K-Means with DBSCAN and Hierarchical Clustering
- Reduce dimensions using PCA for visualization
- Build an interactive dashboard with Streamlit
- Deploy the customer segmentation model

---

## Author

Created by **Oussama** as part of my Machine Learning portfolio.
