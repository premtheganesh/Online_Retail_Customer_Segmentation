# Online Retail Customer Segmentation with RFM and Clustering

## Business Objective
The goal of this project is to segment customers using transactional data from an online retail store. This enables the business to identify customer groups such as high spenders, frequent buyers, and at-risk clients, which can be targeted with personalized marketing strategies.

## Overview
This Jupyter Notebook (`CleanCode.ipynb`) performs customer segmentation on the "Online Retail" dataset using RFM (Recency, Frequency, Monetary) analysis combined with clustering algorithms. The pipeline includes data loading, cleaning, RFM calculation, clustering with K-Means, Hierarchical Clustering, and DBSCAN, followed by model evaluation and visualization.

Key steps:
- Data preprocessing and cleaning.
- RFM metric computation.
- Application of unsupervised clustering models.
- Evaluation using silhouette scores.
- Visualization of results and comparisons.

## Dependencies
The notebook requires the following Python libraries:
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn (for preprocessing, clustering, and metrics)
- scipy (for hierarchical clustering)

Install them using:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy
```

## Dataset
The notebook uses the `Online Retail.xlsx` dataset (not included in this repository). Download it from sources like UCI Machine Learning Repository or Kaggle. Place it in the same directory as the notebook.

- **Data Cleaning**: Removes cancellations (InvoiceNo starting with 'C'), null CustomerIDs, and handles returns separately.
- **Features Added**: TotalPrice, InvoiceMonth, InvoiceHour, InvoiceYear.

## Key Sections

### 1. Data Loading and Cleaning
Loads the Excel file, cleans data by removing invalid entries, and computes additional features like TotalPrice.

### 2. Exploratory Data Analysis (EDA)
Includes visualizations such as top products bar plot (example shown in the notebook).

### 3. RFM Analysis
Calculates Recency, Frequency, and Monetary values for each customer.

### 4. Clustering Models
Applies and compares three unsupervised models:
- **K-Means Clustering**: Identifies 4 balanced clusters.
- **Hierarchical Clustering**: Similar structure but with some micro-clusters.
- **DBSCAN**: Often results in fewer meaningful clusters due to data uniformity.

### 5. Model Evaluation
- Computes silhouette scores for each model.
- Visualizes score comparisons in a bar plot.
- Concludes that K-Means performs best (highest silhouette score ~0.69).

### 6. Visualizations
- Bar plots for silhouette score comparison.
- Additional plots for cluster distributions, average spend, etc. (truncated in the provided document).

### 7. Final Summary
- K-Means is recommended for balanced, actionable segments.
- Insights for business: Reduce churn, improve marketing ROI, increase repeat purchases.

## How to Run
1. Ensure dependencies are installed.
2. Download and place `Online Retail.xlsx` in the notebook directory.
3. Open `CleanCode.ipynb` in Jupyter Notebook or JupyterLab.
4. Run cells sequentially.

Note: Some outputs (e.g., plots) are displayed inline. The notebook is stateful, so previous cells affect later ones.

## Results and Insights
- **Best Model**: K-Means, with well-balanced clusters distinguishing high-value, at-risk, and occasional customers.
- **Silhouette Scores**:
  - K-Means: ~0.69
  - Hierarchical: ~0.65
  - DBSCAN: ~0.61 (often only 1 valid cluster)
- Business Applications: Targeted marketing, churn reduction, personalized strategies.
