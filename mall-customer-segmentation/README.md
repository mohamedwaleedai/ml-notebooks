# Mall customer segmentation

Clusters mall customers by annual income and spending score with K-Means and compares the result with DBSCAN.

The dataset is `Mall_Customers.csv` (200 customers; CustomerID, Gender, Age, Annual Income (k$), Spending Score (1-100)), the Kaggle "Mall Customer Segmentation Data" file. It is not included; place it next to the notebook. The two numeric features are standardised, the elbow method over k = 1 to 10 is read visually to pick k = 5, and K-Means (`random_state=42`) gives clusters whose mean spending scores are 49.5, 82.1, 79.4, 17.1 and 20.9. DBSCAN (`eps=0.5`, `min_samples=5`) finds 2 clusters of 157 and 35 customers and labels 8 as noise. No silhouette score or other cluster-quality metric is computed.
