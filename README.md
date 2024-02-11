# Module 19 Challenge: Clustering Analysis Using KMeans and PCA 
The purpose of this challenge is to apply unsupervised learning algorithms in order to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

## Part 1: Prepare the Data
The first step in this analysis is to process the data so that it can be used with KMEans and PCA. To do this, I used StandardScaler() from the scikict-learn library to normalize the data in the provided csv file (found in Starter_Code/Resources/crypto_market_data.csv). I created a new dataframe with the scaled data and set the cryptocurrency name (coin_id) as the index.

## Part 2: Find the Best Value for k Using the Original Scaled Data 
The next part of this analysis is to find the best value for k (that is, the optimal number of clusters) using the elbow method. I created a list to hold the inertia values, another list of k values ranging from 1 tp 11, and ran a for loop that computed the inertia for each k value and populated the inertia list. With this data, I created a dictionary and plotted a line chart showing each inertia value for each k value to determine which value was the best. This chart found the best value for k to be 4.

## Part 3: Cluster Cryptocurrencies with K-means Using the Original Scaled Data 
The next step is to cluster the various cryptocurrencies with the determined optimal k value. To do this, I initialized the K-means model with k=4, fit the model with the scaled dataframe created in Part 1, and predicted the clusters with this dataframe. I created a copy of the scaled data with an added column for cluster predictions, and plotted these values in a scatter plot where x-axis=price_change_percentage_24h, y-axis=price_change_percentage_7d, and graph points are colored according to the K-means labels.

## Part 4: Optimize Clusters with Principal Component Analysis 
In this step, I optimized the clusters by running a PCA with the features reduced to only three principal components. I retrieved the explained variance from the PCA, which was approximately 90%. This means that about 90% of the information in the original data can be attributed to the sum total of these three principal components, which means I will retain almost all of the information while analyzing in a simplified format. This reduces extra noise and allows us to focus on the most important components of this analysis. 

After finding the explained variance, I created a dataframe with the PCA data and added the cryptocurrency names ("coin_id") from the original dataframe as the index.

## Part 5: Find the Best Value for k Using the PCA Data 
In this part, I follow the same steps as in Part 2, but this time using the PCA data instead of the original scaled data. The generated line chart shows that the best value for k is 4, which is the same as was found in Part 2. 

## Part 6: Cluster Cryptocurrencies with K-means Using the PCA Data
In this part, I follow the same steps as in Part 3, but this time using the PCA data instead of the original scaled data. Additionally, when creating the scatter plot I used x-axis=PC1 and y-axis=PC2. The results of this analysis show that when using fewer features to cluster the data, there is a reduction in noise and a more clear grouping for predictions.
