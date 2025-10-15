# Customer Segmentation Using RFM and K-Means Clustering  

## 1. Project Overview  

This project applies data-driven customer segmentation using **RFM (Recency, Frequency, Monetary) analysis** combined with **K-Means clustering**.  
The objective is to identify and categorize customer behavioral patterns from transaction data of a retail **Superstore dataset**, enabling targeted marketing, retention strategies, and personalized engagement.  

The approach operationalizes advanced analytics and visualization to support **data-driven decision-making in customer relationship management (CRM)**.  

## 2. Business Objective  

Organizations frequently struggle to allocate marketing resources efficiently due to limited visibility into customer purchase behavior.  
This project demonstrates how data science can optimize marketing investment by identifying segments such as:  

- **Best / VIP Customers** – High-value and high-frequency spenders.  
- **Loyal Customers** – Regular buyers with strong brand retention.  
- **Potential / Regular Customers** – Moderate value, high opportunity for upselling.  
- **At-Risk / Lost Customers** – Previously active customers showing churn indicators.  

The resulting segmentation drives **personalized marketing campaigns**, **customer lifetime value prediction**, and **churn mitigation**.  

## 3. Dataset Description  

The dataset used is a **sample of transactional data** from a global retail superstore.  
Each record represents a unique purchase event, containing the following key attributes:  

| Field Name | Description |
|-------------|-------------|
| `CustomerID` | Unique customer identifier |
| `InvoiceNo` | Transaction ID |
| `InvoiceDate` | Date of purchase |
| `Quantity` | Number of items purchased |
| `UnitPrice` | Price per item |
| `TotalAmount` | Derived feature (`Quantity × UnitPrice`) |

Data cleaning and aggregation were performed to ensure customer-level summarization for RFM modeling.  

## 4. Methodology  

### Step 1: Data Preprocessing  
- Handled null values and removed non-relevant transactions (e.g., returns or negative values).  
- Aggregated transactions by customer to compute total spend, transaction count, and last purchase date.  
- Calculated RFM metrics:  
  - **Recency** = Days since last purchase  
  - **Frequency** = Count of transactions  
  - **Monetary** = Total revenue contributed  

### Step 2: Feature Scaling and Outlier Handling  
- Applied **IQR filtering** for outlier reduction.  
- Standardized RFM variables using **StandardScaler** to ensure balanced feature weighting before clustering.  

### Step 3: K-Means Clustering  
- Employed the **Elbow Method** and **Silhouette Score** to determine the optimal number of clusters.  
- Cluster centroids were interpreted as segment profiles.  

### Step 4: Segmentation Labeling  
- Clusters were analyzed and mapped into business-relevant segments:  
  - High Monetary + Low Recency + High Frequency → **Best / VIP Customers**  
  - Moderate Monetary + Medium Recency → **Loyal Customers**  
  - Low Frequency + Low Monetary + High Recency → **At-Risk / Lost Customers**  

## 5. Visualization and Dashboard  

A **Power BI dashboard** consolidates analytical insights for executive-level interpretation.  
Visual components include:  

- **Recency vs Monetary Scatter Plot:** Cluster distribution analysis  
- **Bar Charts:** Frequency and Monetary contribution by segment  
- **Donut Chart:** Revenue share per segment  
- **Summary Table:** Average RFM values and recommended marketing actions  

The dashboard integrates color-coded segmentation to support intuitive data storytelling and decision-making.  

## 6. Model Evaluation  

- Cluster stability and separation were validated through **Silhouette Coefficient** and **intra-cluster variance** analysis.  
- The resulting clusters showed strong differentiation in behavioral metrics, confirming the suitability of K-Means for this RFM dataset.  

## 7. Insights and Strategic Recommendations  

| Segment | Insight | Strategic Action |
|----------|----------|------------------|
| **Best / VIP Customers** | High spenders with frequent purchases | Reward and retain through exclusives and loyalty benefits |
| **Loyal Customers** | Consistent engagement but moderate spend | Encourage referrals and upsell programs |
| **Potential / Regular Customers** | Stable group with growth potential | Target with offers and personalized campaigns |
| **At-Risk / Lost Customers** | Low frequency and recent inactivity | Re-engage through win-back and feedback campaigns |

This segmentation framework enables **precision marketing**, **resource optimization**, and **customer lifetime value enhancement**.  

## 8. Technical Stack  

- **Programming:** Python (Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn)  
- **Modeling:** RFM Analysis, K-Means Clustering  
- **Visualization:** Power BI (interactive dashboard)  
- **Versioning:** Jupyter Notebook (`.ipynb`)  
- **Environment:** Python 3.10+  

## 9. How to Run  

1. **Clone the repository:**
   
   git clone https://github.com/<your-username>/Customer-Segmentation-by-RFM-Kmeans.git
   cd Customer-Segmentation-by-RFM-Kmeans
Install dependencies:

pip install -r requirements.txt
Run the notebook:

jupyter notebook RFM_KMeans.ipynb
Load the processed dataset into Power BI to reproduce the dashboard visuals.

10. Future Enhancements
Integrate predictive modeling to forecast segment migration over time.

Develop automated Power BI refresh pipeline using Python connectors.

Extend segmentation with demographic and behavioral attributes for multidimensional analysis.

Integrate recommendation engine for personalized product suggestions.

**Next Step for You:**
1. In VS Code or Jupyter file explorer, create a new file → name it **`README.md`**.  
2. Paste the above content inside it.  
3. Save → commit → push to GitHub.  
