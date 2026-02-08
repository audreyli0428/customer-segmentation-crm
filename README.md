# Customer Segmentation & CRM Recommendation

## Overview
This project demonstrates an end-to-end customer segmentation workflow using
credit card behavioral data. By combining data cleaning, exploratory data
analysis, clustering, and business interpretation, the project translates
raw customer behavior into actionable CRM (Customer Relationship Management)
strategies.

The goal is not only to identify statistically meaningful customer segments,
but also to bridge analytical results with real-world business decision-making.

---

## Business Problem
Companies often collect large volumes of customer transaction data, yet struggle
to convert this data into clear, actionable insights. Treating all customers
uniformly can lead to inefficient marketing spend, missed retention opportunities,
and unmanaged financial risk.

This project addresses the following questions:
- Can customers be grouped based on distinct behavioral patterns?
- How do these segments differ in terms of value, engagement, and risk?
- How can segmentation results be translated into concrete CRM actions?

---

## Dataset
The dataset contains aggregated credit card usage information at the customer level,
including:
- Spending and balance metrics
- Purchase and cash advance behavior
- Usage frequency and payment discipline indicators

Each row represents a customer, summarized over a fixed observation period.
The dataset is well-suited for behavioral segmentation but does not include
a predefined target variable.


---

## Methodology

### 1. Data Cleaning
- Removed non-informative identifier columns
- Analyzed missing values and applied median imputation to skewed monetary variables
- Preserved the full customer population to avoid unnecessary data loss
- Exported a clean dataset for downstream analysis

**Notebook:** `01_data_cleaning.ipynb`

---

### 2. Exploratory Data Analysis (EDA)
- Analyzed distributions of spending, frequency, and payment behavior
- Identified strong right-skewness in monetary variables
- Examined correlations to detect redundant features
- Used EDA insights to guide feature selection for clustering

**Notebook:** `02_eda.ipynb`

---

### 3. Customer Segmentation
- Selected a reduced, interpretable feature set representing distinct behavioral dimensions
- Applied feature scaling using standardization
- Evaluated the number of clusters using:
  - Elbow Method
  - Silhouette Analysis
  - Business interpretability considerations
- Applied K-Means clustering with k = 4
- Interpreted clusters based on behavioral profiles

**Notebook:** `03_segmentation.ipynb`

---

### 4. CRM Recommendation
- Translated customer segments into business-relevant personas
- Designed targeted CRM objectives for each segment
- Mapped clusters to actionable CRM strategies
- Produced a final dataset combining segmentation results and CRM recommendations

**Notebook:** `04_crm_recommendation.ipynb`

---

## Customer Segments (Summary)

- **Cluster 0 — Low Engagement Customers**  
  Low spending and infrequent usage with limited revenue contribution.

- **Cluster 1 — High-Value Active Spenders**  
  Highly engaged customers with strong purchase activity and high revenue potential.

- **Cluster 2 — Cash-Advance-Oriented / Higher-Risk Customers**  
  Heavy reliance on cash advances and lower payment discipline, indicating elevated risk.

- **Cluster 3 — Disciplined / Financially Responsible Customers**  
  High full payment ratios, low risk, and strong long-term value potential.

---

## Business Impact
This project shows how customer behavioral data can be transformed into actionable
business insights through segmentation.

Instead of applying one-size-fits-all strategies, the resulting customer segments
enable differentiated CRM actions aligned with engagement level, customer value,
and financial risk. The final outputs are designed to be directly usable for
campaign planning, retention strategies, and risk management discussions.

---

## Key Takeaways
- Customer behavior is highly heterogeneous, with clear differences in spending,
  engagement, and payment discipline.
- Correlation-based feature selection improves clustering interpretability by
  reducing redundancy.
- Selecting the number of clusters requires balancing statistical metrics with
  business usability.
- Translating segmentation results into CRM actions significantly increases
  the practical value of the analysis.
- An end-to-end analytical workflow can effectively bridge data analysis and
  real-world decision-making.


---
```
## Project Structure

├── data/
│ ├── raw/
│ │ └── CreditCard_STM.csv
│ └── processed/
│ └── creditcard_clean.csv
│
├── notebooks/
│ ├── 01_data_cleaning.ipynb
│ ├── 02_eda.ipynb
│ ├── 03_segmentation.ipynb
│ └── 04_crm_recommendation.ipynb
│
├── outputs/
│ └── tables/
│ ├── customer_with_clusters.csv
│ └── customer_with_clusters_and_crm.csv
│
└── README.md
```
---

## Deliverables
- `customer_with_clusters.csv`  
  Customer-level dataset with assigned segmentation labels.

- `customer_with_clusters_and_crm.csv`  
  Final dataset including both customer segments and recommended CRM actions,
  ready for downstream business use.

---

## Tools & Technologies
- Python
- pandas, numpy
- scikit-learn
- matplotlib, seaborn

---

## Author
Hao Ju Li (Audrey)