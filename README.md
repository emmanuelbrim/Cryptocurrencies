# CRYPTOCURRENCIES
_Analyzing the Crypto-market to Provide Advisory Service on Investment_


## Overview of the Project

The investment world was taken by storm by the rise of the cypto-market in 2018, especially the Bitcoin boom. Now a dozen of such currencies exist and as regulators find it difficult to control the best trading of these currencies so are investors stuck in the dilema of which one to trade in. 
Martha from Accountability Accounting has been tasked by her firm to analyze and provide a report of the current currencies on the market. 
This will help the company offer the best option when it comes to investing in the crypto-market to their clients.
This project was to assist the researcher with creating a unsupervised machine learning model that will classify and provide the best results from a cryptocurency dataset.

Resources:
1. Anaconda jupyter notebook
2. Pandas library
3. Scikit-learn


## Results

- Preprocessing 

The data was read-in using pandas read_csv method.
The data provided in the dataframe was consideered not ideal, since unsupervised learning models only relied on numerical data. It was therefore required that the data get cleaned before use. 

The first step was to filter the dataframe to hold only currencies that were being traded as crypto_df.

Next was to remove all currencies that didnot have a working Algorithm using the pandas dropna. Then the "IsTrading" column was dropped and a new dataframe holding only currencies which were mined as mint_crypto_df was produced by filtering the crypto_df dataframe by "TotalCoinMind > 0", using the loc function.

The coinName column was dropped from the mint_crypto_df dataframe to produce data ready to be transformed.
Using get_dummies function the categorical features of the data was transformmed to numerical. Likewise the data was scaled using the standardScaler function from scikit-learn. The final dataframe "X" held all scaled data.

Below is an imageof code and results of scaling the data.
![]()

- Dimentional Reduction using PCA

The analysis required the reduction of the dimensions to managable components for the model.
The Principal component analysis (PCA) was used to achieve this. 
From SKlearn.decomposition class the PCA was imported and initialized as pca and used to transform the components of the data to 3.

![]()

- Clustering

The third stage of the analysis was to cluster the cryptocurrency data to find trends.
The elbow method was used to plot a line chart of possible clusters by inertia. The chart showed that with a cluster of 4 the model based on KMeans will produce the best accuracy. 
Predictions were therfore generated using this metric and then a dataframe; clustered_df was produced to show the principal components and the predictions with the original dataframe X.

![]()


- Visualization

To present the final results to the board required creating a dashboard to visualize the data. Plotly's express class and pandas hvplot was used to produce graphs that depict the results of the classification model. 


![]()


## Summary
Unsupervised Learning may not be the best answer to every data analysis. It is clear that the model will require more tuning to generate the best classification. Similarly additional data might be required to fine tune the model. It is not always the case that unsupervised model will work where supervised have failed hence other models could be used as well to produce better results. 


