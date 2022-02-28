![Header](http://www.softwaresamurai.org/wp-content/uploads/2018/02/Crypto_Header_3.png)

# CRYPTOCURRENCIES

## Objective

Create a report and classification system including which cryptocurrencies are in circulation. Use unsupervised learning to group the cryptocurriencies into an  buckets of unknown criteria. Present the cluster results visually to the board. 

## Procedure

**Deliverable 1: Preprocessing Crypto Data**
1. Read the Crypto CSV file to a DataFrame
2. Drop the **IsTrading** column
3. Remove rows with null values
4. Filter **crypto_df** to only show coins that have been mined
5. Create a DataFrame holding the cryptocurrency names using the **crypto_df** as an index.
6. Remove **coin_name** from the **crypto_df** 
7. Use the **get_dummies** method to create variables for **Algorithm** and **ProofType** storing in a dataframe named 'X'
8. Use the StandardScaler **fit_transform()** function to standardize the features from 'X'

**Deliverable 2: Apply PCA Algorithm**
9. Apply [PCA](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html) to reduce the dimensions into 3 principal components
10. Create a new dataframe called **pca_df** that includes the columns for **PC 1, PC 2 & PC 3** and using the crypto_df as the index.

**Deliverable 3: Clustering Cryptocurrencies using K-means**
11. Create a elbow curve for the **pca_df** to find the best value for K
12. Use the **pca_df** and run the [K-means algorithm](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html) to make predictions of the K clusers for the cryptocurrency data.
13. Create a dataframe called clustered_df by concatenating the crypto_df and pca_df on the same columns (index same as crypto_df)
14. Add the **CoinName** column created in the previous step in Deliverable 1.
15. Add **Class** which holds the results of the predictions from the K-means algorithm.

## Visualization Results

### Elbow Curve
![Elbow Curve]()

### 3D Scatter Plot with Clusters showing Coin Name and Algorithm
![3D Plot]()

### Table of Cryptocurrencies
![Table of Crypto]()

### Scatter Plot for Total Coins Mined and Total Coin Supply
![Scatter Plot]()

*For tabular and printed results please refer to the [JuPyTer Notebook file (.pynb)](https://github.com/srfassihi/Cryptocurrencies/blob/main/crypto_clustering.ipynb#L20) attached to this repo.*


