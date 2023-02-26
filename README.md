# K-means-Clustering-Using-R

This program performs K-means clustering on a dataset of white wine characteristics. The steps of the program are as follows:

# Step 1: Data import
The program first imports necessary libraries and reads in the white wine data from an Excel file using the read_xlsx function from the readxl library. It then creates a boxplot of the original data.

# Step 2: Remove the extreme outliers
The program then identifies and removes extreme outliers in the dataset. It first identifies outliers for the "residual sugar" variable by calculating the interquartile range (IQR) and using a threshold of 1.5 times the IQR to determine bounds for outliers. It then identifies outliers for the "free sulfur dioxide" and "total sulfur dioxide" variables using the same method. Outliers are removed from the dataset and stored in a new dataframe called "no_outliers". The program then creates a boxplot of the cleaned data.

# Step 3: Scaling
The program then scales the cleaned data using the scale function to ensure that variables with different units or scales do not dominate the clustering results.

# Step 4: Determining the number of clusters
The program then uses the NbClust function to determine the optimal number of clusters for the dataset using k-means clustering. The function calculates nine different clustering indices for each potential number of clusters (ranging from 2 to 8) and outputs a bar plot indicating the number of clusters chosen by each index. The program then calculates the within-group sum of squares (WSS) for each potential number of clusters and outputs a plot showing the relationship between the number of clusters and the WSS.

# Step 5: K-means clustering
Based on the results of the previous step, the program chooses to perform K-means clustering with k=2, 3, 4, and 5. For each value of k, the program performs K-means clustering using the kmeans function and stores the results in a variable (e.g. fit.km2, fit.km3). The program then evaluates the clustering results using the confusion matrix, Adjusted Rand Index (ARI), and parallel coordinates plot.

# Step 6: NbClust with Manhattan distance
Finally, the program performs NbClust again, this time using the Manhattan distance metric, and calculates all clustering indices for k=2 to k=5.
