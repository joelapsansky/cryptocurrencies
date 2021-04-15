# Cryptocurrencies
Finished Deliverables:  
[Crypto Clustering](/crypto_clustering.ipynb)  
## Overview
Given a provided cryptocurrency dataset, use different techniques to cluster crypto components and uncover patterns.
## Procedure
First, preprocess the data.  In this case, we dropped unnecessary columns, dropped currencies that aren't trading, changed data types, and only kept coins that have been mined.  For example, this is how to keep mined coins greater than zero:  
  
```
# Keep the rows where coins are mined.
crypto_df = crypto_df[crypto_df['TotalCoinsMined'] > 0]
crypto_df.shape
```  
  
We also scaled data using the StandardScaler:  
```
crypto_scaled = StandardScaler().fit_transform(X)
```  
  
Next, we reduced data dimensions using PCA (Principal Component Analysis).  Finally, we used K-means to cluster, and then visualized the data after creating clean data frames.

## Results and Summary
There are 532 tradable cryptocurrencies.  Out of the 4 classes, 2 of them comprise 6 cryptocurrencies; the remaining 526 fall into the other 2 classes.  
  
This scatter plot grouped by class shows mined coins on the x-axis and supply of coins on the y axis:  
  
![Scatter Plot](/Images/scatter.png "Scatter Plot")  
  
It is clear that this model does not do a great job of clustering because there is plenty of overlap between the two main classes.  
  
Crypto is difficult to cluster given these features.  While it is valuable to try grouping using a different number of clusters, it is also advisable to see if there are other crypto features available to use in a new model.
