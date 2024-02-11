# Module 19 Challenge: Clustering Analysis Using KMeans and PCA 
The purpose of this challenge is to apply unsupervised learning algorithms in order to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

## Part 1: Prepare the Data
The first step in this analysis is to process the data so that it can be used with KMEans and PCA. To do this, I used StandardScaler() from the scikict-learn library to normalize the data in the provided csv file (found in Starter_Code/Resources/crypto_market_data.csv). I created a new dataframe with the scaled data and set the cryptocurrency name (coin_id) as the index.

## Part 2: Find the Best Value for k Using the Original Scaled Data 
The next part of this analysis is to find the best value for k (that is, the optimal number of clusters) using the elbow method. I created a list to hold the inertia values, another list of k values ranging from 1 tp 11, and ran a for loop that computed the inertia for each k value and populated the inertia list. With this data, I created a dictionary and plotted a line chart showing each inertia value for each k value to determine which value was the best. This chart found the best value for k to be 4.

## Part 3: Cluster Cryptocurrencies with KMeans Using the Original Scaled Data 
The next step is to cluster the various cryptocurrencies with the determined optimal k value. To do this, I initialized the KMeans model with k=4, fit the model with the scaled dataframe created in Part 1, and predicted the clusters with this dataframe. I created a copy of the scaled data with an added column for cluster predictions, and plotted these values in a scatter plot where x-axis=PC1, y-axis=PC2, and graph point colors=KMeans values.
