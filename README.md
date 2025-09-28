# Online-Shoppers-Purchasing-Intention


```
# 🛒 Online Shopping Intention Analysis with K-Means

This project applies **Unsupervised machine learning (K-Means clustering)** to analyze customer behavior in online shopping sessions.  
The goal is to identify patterns in **product-related duration** and **bounce rates** that may indicate whether a visitor is likely to make a purchase.
---

## 📌 Project Overview
- **Dataset**: `online_shoppers_intention.csv`  
- **Objective**: Cluster customers into groups (e.g., uninterested vs. target customers) and evaluate clustering performance against the actual `Revenue` label.  
- **Techniques Used**:
  - Data preprocessing (handling missing values)
  - K-Means clustering with the **Elbow Method**
  - Visualization of clusters
  - Evaluation with **Adjusted Rand Index** and **Confusion Matrix**

---

## ⚙️ Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/your-username/online-shopping-intention.git
cd online-shopping-intention
pip install -r requirements.txt
```

**requirements.txt**
```
numpy
pandas
matplotlib
seaborn
plotly
scikit-learn
scikit-plot
scipy
```

---

## 🚀 Usage

Run the script:

```bash
python shopping_intention.py
```

This will:
1. Load the dataset  
2. Handle missing values  
3. Perform clustering with K-Means  
4. Plot the **Elbow Method** graph  
5. Visualize clusters of customers  
6. Evaluate clustering with **Adjusted Rand Index** and **Confusion Matrix**

---

## 📊 Workflow

### 1. Data Preprocessing
- Load dataset with `pandas`
- Check for missing values → fill with `0`
- Select features:
  - `ProductRelated_Duration` (column index 5)
  - `BounceRates` (column index 6)

### 2. K-Means Clustering
- Use **Elbow Method** to determine optimal clusters (1–10)
- Fit K-Means with `n_clusters=2`
- Assign labels:
  - **Cluster 0** → Uninterested Customers
  - **Cluster 1** → Target Customers

### 3. Visualization
- Scatter plot of clusters with centroids
- X-axis: `ProductRelated Duration`
- Y-axis: `Bounce Rates`

### 4. Evaluation
- Encode `Revenue` column with `LabelEncoder`
- Compare predicted clusters with true labels
- Metrics:
  - **Adjusted Rand Index** → similarity between clustering and ground truth
  - **Confusion Matrix** (normalized & non-normalized)

---

## 📈 Results

- **Cluster Insights**:
  - Cluster 0: High bounce rate, low product duration → uninterested customers
  - Cluster 1: Low bounce rate, high product duration → potential buyers

- **Adjusted Rand Index**: Low → clustering does not strongly align with actual purchase outcomes

- **Confusion Matrix**:
  - Non-purchasing sessions mostly classified correctly
  - Purchasing sessions often misclassified → highlights limitations of unsupervised clustering

---

## 🔮 Future Work
- Apply **supervised models** (Logistic Regression, Random Forest, XGBoost) for better prediction
- Engineer new features (session duration, traffic source, seasonal trends)
- Use **dimensionality reduction (PCA, t-SNE)** for visualization

---
## Dataset
[online_shoppers_intention.csv](https://github.com/user-attachments/files/22582300/online_shoppers_intention.csv)

## 📚 Reference
- Inspired by: [Online Shopping Intention Analysis with Python – Aman Kharwal](https://amanxai.com/2020/12/04/online-shopping-intention-analysis-with-python/)
---

✨ *This project demonstrates how clustering can reveal customer behavior patterns, but also why supervised learning is often more effective for predicting purchase intent.*
```
