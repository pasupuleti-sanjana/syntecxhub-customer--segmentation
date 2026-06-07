[README (2).md](https://github.com/user-attachments/files/28675213/README.2.md)
# syntecxhub-customer--segmentation#  Customer Segmentation using K-Means Clustering

> **Syntecxhub Internship Program** — Machine Learning | Task 3 | Project 1

---

##  Project Overview

This project applies **unsupervised machine learning** (K-Means Clustering) to segment mall customers based on their **Age**, **Annual Income**, and **Spending Score**. The goal is to identify distinct customer groups and derive actionable marketing strategies for each segment.

---

##  Repository Structure

```
Syntecxhub_Customer_Segmentation/
│
├── customer_segmentation.py          # Main Python script
├── customer_segments.csv             # Dataset with cluster labels
├── customer_segmentation_analysis.png  # 9-panel visualization
├── segment_report.txt                # Marketing report per segment
└── README.md                         # Project documentation
```

---

##  Dataset

| Feature | Description |
|---|---|
| `CustomerID` | Unique customer identifier |
| `Gender` | Male / Female |
| `Age` | Customer age (18–70) |
| `Annual_Income_k` | Annual income in $k |
| `Spending_Score` | Mall-assigned score (1–100) |

- **200 customers**, **0 missing values**
- Source: Mall Customers dataset (standard ML benchmark)

---

##  Tech Stack

| Library | Purpose |
|---|---|
| `pandas` | Data loading & manipulation |
| `numpy` | Numerical operations |
| `scikit-learn` | Scaling, KMeans, Silhouette score |
| `matplotlib` | Plotting |
| `seaborn` | Heatmap & enhanced visuals |

---

## 🚀 How to Run

### 1. Clone the repository
```bash
git clone https://github.com/<your-username>/Syntecxhub_Customer_Segmentation.git
cd Syntecxhub_Customer_Segmentation
```

### 2. Install dependencies
```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

### 3. Run the script
```bash
python customer_segmentation.py
```

### Outputs generated:
- `customer_segments.csv` — original data with `Cluster` and `Segment` columns appended
- `customer_segmentation_analysis.png` — full 9-panel analysis chart
- `segment_report.txt` — per-segment marketing report printed & saved

---

##  Methodology

### Step 1 — Data Preprocessing
- Checked for nulls and duplicates
- Applied `StandardScaler` to normalize features before clustering

### Step 2 — Choosing Optimal k (Elbow Method)
- Ran K-Means for k = 2 to 10
- Plotted **Inertia** (within-cluster sum of squares) → look for the "elbow"
- Plotted **Silhouette Score** → higher = better-defined clusters
- **Optimal k = 5** confirmed by both metrics

### Step 3 — K-Means++ Clustering
- Used `init='k-means++'` for smarter centroid initialization
- `n_init=20` runs to avoid local minima
- Final **Silhouette Score = 0.356**

### Step 4 — Cluster Profiling & Naming

| Segment | Avg Age | Avg Income | Avg Spending |
|---|---|---|---|
| Careful Spenders | 25 yrs | $26k | 84/100 |
| Young Explorers | 29 yrs | $59k | 56/100 |
| High-Value Targets | 48 yrs | $58k | 53/100 |
| Budget-Conscious | 64 yrs | $98k | 26/100 |
| Affluent Moderates | 48 yrs | $110k | 24/100 |

### Step 5 — Marketing Actions

| Segment | Recommended Strategy |
|---|---|
| **Careful Spenders** | Instalment offers, trust-building campaigns, customer reviews |
| **Young Explorers** | Trend-driven ads, social media promotions, Buy Now Pay Later |
| **High-Value Targets** | VIP programs, personalised luxury offers, retention rewards |
| **Budget-Conscious** | Value deals, loyalty rewards, discount coupons |
| **Affluent Moderates** | Premium product lines, exclusive memberships, VIP events |

---

## Visualizations

The output chart contains **9 panels**:

1. Elbow Method (Inertia vs k)
2. Silhouette Score vs k
3. Annual Income vs Spending Score (scatter by cluster)
4. Age vs Spending Score
5. Age vs Annual Income
6. Cluster Sizes (bar chart)
7. Feature Heatmap (avg Age, Income, Spending per segment)
8. Gender Distribution per Segment
9. Spending Score Distribution (box plots)

---

##  Key Takeaways

- **K-Means++** with k=5 cleanly separates customers into interpretable groups
- **Careful Spenders** (young, low income, high spend) are high-priority targets despite lower income — they're already engaged
- **Affluent Moderates** (high income, low spend) represent the biggest **untapped opportunity**
- Gender is fairly balanced across segments, so gender-neutral campaigns work for most groups

---

## Author

**[Your Name]**
Machine Learning Intern — Syntecxhub
 [your-email@example.com]
 [LinkedIn Profile]

---

## 🏢 About Syntecxhub

Syntecxhub is a forward-thinking company that bridges learning with practical experience, offering internship projects across Web Development, UI/UX Design, Data Science, and more.

> 🌐 [www.syntecxhub.com](https://www.syntecxhub.com) | 📞 +91 63937 80295 | ✉️ info@syntecxhub.com
