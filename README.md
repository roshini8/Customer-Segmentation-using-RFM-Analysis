# 🧠 Customer Segmentation using RFM Analysis + KMeans Clustering

This project performs **Customer Segmentation** using the **RFM model (Recency, Frequency, Monetary)** combined with **KMeans clustering** to identify different customer types and enable targeted business strategies. 

By transforming raw transactional data into RFM metrics and applying unsupervised learning, businesses can personalize engagement and improve profitability.

---

## 🔍 Objective

- Understand different patterns in customer purchasing behavior.
- Segment customers based on their transaction history.
- Build customer personas and recommend strategic marketing actions.
- Visualize the customer base for data-driven business decisions.

---

## 📊 Dataset

The dataset `orders.parquet` includes **3.9M+ order records** and has the following key columns:

| Column Name   | Description                                 |
|---------------|---------------------------------------------|
| `id`          | Unique order ID                             |
| `created_at`  | Timestamp of order placement                |
| `sales_amount`| Monetary value of the order (float)         |
| `customer_id` | Unique identifier for each customer         |

---

## 🧪 Tech Stack

- **Python 3.x**
- **Pandas**, **NumPy**
- **Scikit-learn**
- **Matplotlib**, **Seaborn**
- **PyArrow** for Parquet reading
- **Jupyter Notebook**

---

## 🛠️ Project Workflow

### 1. **Data Preprocessing**
- Load `.parquet` file using `pyarrow`.
- Checked for missing values, data types, and duplicates.
- Converted timestamps to `datetime` objects.

### 2. **Exploratory Data Analysis (EDA)**
- Visualized:
  - Orders over time (daily, monthly)
  - Sales distribution
  - Order counts by day of week

### 3. **RFM Feature Engineering**
Calculated per-customer metrics:
- **Recency**: Days since last purchase.
- **Frequency**: Total number of transactions.
- **Monetary**: Total value spent.

### 4. **Data Scaling**
Used `StandardScaler` to normalize RFM values before clustering.

### 5. **KMeans Clustering**
- Used **Elbow Method** to determine optimal `k = 4`.
- Applied **KMeans** to create 4 distinct customer segments.

### 6. **PCA (Dimensionality Reduction)**
- Applied **Principal Component Analysis (PCA)** to visualize customers in 2D.
- Plotted customer clusters using `PCA1` and `PCA2`.

### 7. **Segment Profiling**
Summarized key characteristics of each cluster:
- Recency (mean/median)
- Frequency (mean/median)
- Monetary value (mean/median)
- Number of customers per cluster

---

## 📌 Cluster Labels

| Cluster ID | Segment Name         | Description |
|------------|----------------------|-------------|
| 0          | Loyal High Spenders  | Frequent, recent buyers with high spend |
| 1          | New Customers        | Recent buyers with low frequency |
| 2          | Churned              | Inactive customers, low recent activity |
| 3          | Occasional Buyers    | Moderate recency, medium value |

---

## 📈 Key Visualizations

- **RFM Scatter Plots**:
  - Recency vs Frequency
  - Frequency vs Monetary
  - Recency vs Monetary

- **Elbow Method Chart**:
  - Helps determine optimal number of clusters (k)

- **PCA Scatter Plot**:
  - Visualizes clusters in 2D space

- **Cluster-wise Distribution**:
  - Frequency vs Monetary by cluster

---

## 🧠 Insights & Business Use Cases

- 🎯 **Target Loyal High Spenders** with exclusive offers or VIP rewards.
- 👋 **Re-engage Churned Customers** via win-back campaigns or surveys.
- 🚀 **Onboard New Customers** with personalized onboarding flows.
- 🛍️ **Upsell Occasional Buyers** with bundle offers and recommendations.

---
# 🏃‍♀️ How to Run

### 1. Download the Project
- Download or clone the repository to your local machine.

### 2. Add the Dataset
- Make sure the `orders.parquet` file is in the same folder as the notebook.

### 3. Change the File Path (if needed)
- In the notebook, find this line:

```python
df = pd.read_parquet("orders.parquet")
```

- If your dataset is stored elsewhere, update the path like this:
```python
df = pd.read_parquet(r"C:\path\to\your\orders.parquet")
```

