# Flight Customer Clustering

## Introduction
In this project we use dataset from flight.csv that I have uploaded it too in this repository. There are 23 columns and 62000+ rows in this dataset, with each rows represent 1 user or individu. In this project we need to make cluster for flight customer based on how long they used our facilities and how much the transactions they did in order to make promo or other program to get more profit.

## Exploratory Data Analysis (EDA)
- There are 22 columns with 18 of them are numericals, 4 of them are categorical and 4 others are in datetime format.
- Convert the time column to datetime format.
- Fill missing values in categorical data with the mode, while numerical data will be filled with the median.
- The `avg_discount` column should have a maximum value of 1, where a value of 1 represents a 100% discount. Any value greater than 1 will be dropped.
- Drop the `WORK_PROVINCE` and `WORK_CITY` columns, as they have a large number of categories.
- The `WORK_COUNTRY` column is predominantly filled with the value "CN." It will be transformed into a boolean format, where the value 1 represents "CN" and 0 represents any other country.

### Multivariate Analysis
- There is a significant amount of data with very high correlation, which may indicate redundant information.
- `BP_SUM`, `SEG_KM_SUM`, and `Points_Sum` exhibit high correlation and have identical values. To avoid redundancy, one of them will be selected, while the others will be dropped.
- `AGE`, `AVG_INTERVAL`, and `MAX_INTERVAL` will be dropped as they have low correlation with other features.

## Pre-Processing
- Fixing Data Types.
- Handle Missing Values.
- Handle Outliers.
- Feature Engineering.
- Drop Unimportant Columns.
- Feature Selection.
- Standardization.

## Modelling
- Unsupervised Learning: Clustering
- Shilouette Score
- Elbow Method
- K-Means Clustering
- Visualization

## Insight and Recommendation
- Got 4 clusters:
- Cluster 0 (Potential Customer):
  Customers in this cluster can be considered potential as they are predominantly new customers with low transaction distances. Additionally, this cluster has the highest number of customers. However, the frequency of purchases and the number of trips are low.
- Cluster 1 (Priority Customer):
  In this cluster, we find long-standing members with low transaction distances. However, the frequency of purchases and the number of trips are low. Therefore, customers in this cluster need further attention.
- Cluster 2 (General Customer):
  Customers in this cluster exhibit characteristics of typical customers who have been members for a considerable time. However, they only travel at certain times, which can be seen from the long periods without transactions, as well as the lowest frequency of purchases and number of trips compared to other clusters.
- Cluster 3 (Loyal Customer):
  Customers in this cluster can be categorized as loyal customers due to their high frequency and number of trips, as well as very short average transaction distances.
  
### Recommendation
- Creating a loyalty program where customers who travel more frequently will receive greater discounts.
- Creating promotions and discounts based on customer segmentation.
