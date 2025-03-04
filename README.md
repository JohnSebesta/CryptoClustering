# CryptoClustering
Overview

In this project, we are tasked with analyzing and clustering cryptocurrency data using K-means clustering and Principal Component Analysis (PCA). The goal is to process and normalize the data, find the optimal number of clusters using the elbow method, and then compare clustering results based on different feature sets: the original scaled data and the reduced PCA features. This project also involves visualizing the clusters and understanding the impact of dimensionality reduction on the clustering process.

The project is broken into the following steps:

Data Preparation: Normalizing the cryptocurrency data and preparing it for clustering.
Finding the Best Value for k: Using the elbow method to determine the optimal number of clusters.
Clustering with K-Means: Applying K-means clustering to group the data based on different feature sets.
Optimization with PCA: Using PCA to reduce the feature dimensions and comparing clustering results.
Comparison: Evaluating the impact of dimensionality reduction on clustering.
Methodology

Part 1: Prepare the Data
Normalize the Data:
The StandardScaler() from scikit-learn is used to scale the cryptocurrency data from the CSV file.
A DataFrame is created with the normalized data, and the "coin_id" is set as the index.
Preview the Data:
The first five rows of the scaled DataFrame should display the normalized data values for the different features.
Part 2: Find the Best Value for k Using the Scaled DataFrame
Elbow Method:
A range of possible k values (from 1 to 11) is created, and an empty list is initialized to store the inertia values for each k.
A loop iterates through the k values, computing the inertia for each and storing it.
A dictionary is created to prepare data for plotting the elbow curve.
A line chart is plotted with inertia values for different k values, and the optimal k is determined based on the "elbow" in the plot.
Optimal k:
The best value for k is identified by visually inspecting the elbow curve.
Part 3: Cluster Cryptocurrencies with K-Means Using the Scaled DataFrame
K-Means Clustering:
The K-means model is initialized with the best value for k from the elbow method.
The model is fitted using the scaled DataFrame, and clusters are predicted for the cryptocurrencies.
A copy of the scaled DataFrame is created, and a new column is added with the predicted clusters.
Visualization:
A scatter plot is created using hvPlot, with the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
The points are colored by their predicted cluster labels, and the "coin_id" is added to the hover information.
Part 4: Optimize Clusters with Principal Component Analysis (PCA)
Apply PCA:
PCA is performed on the scaled DataFrame to reduce the number of features to three principal components.
The explained variance is retrieved to understand the proportion of variance attributed to each principal component.
PCA DataFrame:
A new DataFrame is created with the scaled PCA data, and the "coin_id" from the original DataFrame is used as the index.
The first five rows of the scaled PCA DataFrame are displayed.
Part 5: Find the Best Value for k Using the PCA DataFrame
Elbow Method on PCA Data:
The elbow method is applied again to the PCA-reduced DataFrame to determine the best k value.
A plot of inertia values for different k values is created to find the optimal number of clusters.
Comparison of k Values:
The best value for k is compared between the original scaled data and the PCA data.
Part 6: Cluster Cryptocurrencies with K-Means Using the PCA DataFrame
K-Means on PCA Data:
K-means clustering is applied to the PCA-reduced data using the best value of k found from the PCA Data.
The predicted clusters are stored in a new column in the scaled PCA DataFrame.
Visualization:
A scatter plot is created with "PC1" on the x-axis and "PC2" on the y-axis, with the points colored by the predicted clusters.
Part 7: Impact of Using Fewer Features
The impact of reducing the number of features using PCA is assessed by comparing the clustering results with those obtained from the original data.
The benefits and limitations of using fewer features for clustering are discussed.
Results

Data Normalization:
The data was successfully normalized using StandardScaler(). The scaled DataFrame was created with the "coin_id" set as the index.
Elbow Method for k:
The optimal value for k was found using the elbow method, both for the original scaled data and the PCA-reduced data.
K-Means Clustering:
The K-means model was applied to both the original scaled data and the PCA-reduced data.
Clusters were predicted and visualized with scatter plots, showing how the cryptocurrencies are grouped.
PCA and Explained Variance:
The PCA transformation reduced the feature space to three principal components, and the explained variance showed the proportion of variance captured by each component.
Impact of PCA:
The analysis showed that reducing the number of features to three principal components slightly altered the clustering results, but it made the model more efficient and easier to visualize.

References
ChatGpt
Xpert Learning Assistant
The Tutor Fred Logan
