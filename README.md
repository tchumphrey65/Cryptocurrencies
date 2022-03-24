# Cryptocurrencies

## Purpose

Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers.  The cryptocurrency market is dynamic and complicated creating some challenge for Accountability Accounting.  We have been hired to create an analysis to aid them in their entry into the cryptocurrency market.

We have been requested to create a report that includes what cryptocurrencies are trading on the  market and how to group them to create a classification system for this new investment.  We are also being asked to create visualizations of the crptocurrency data to aid in presenting this information to clients of Accountability Accounting.

## Analysis 

### Load and preprocess the Data for PCA
#### Preprocessing Actions
1) Cryptocurrencies not being traded are removed.
2) Drop the IsTrading column.
3) Drop all the rows that have at least one null.
4) All rows removed where coins are not being mined.
5) The CoinName column is dropped.

1) Remove Currencies currently not being traded

![image](https://user-images.githubusercontent.com/91839403/159948709-0d69c207-e80c-48dd-91db-af1c34a5c050.png)

![image](https://user-images.githubusercontent.com/91839403/159948779-4b45c4f0-fd74-4a41-9306-c73b3fd29702.png)

2) Drop the IsTrading column

![image](https://user-images.githubusercontent.com/91839403/159949034-48e8485e-03d1-4ae5-9755-2c1194e7adb6.png)

![image](https://user-images.githubusercontent.com/91839403/159949119-462943da-484c-42ee-b22b-e51d8b4d1040.png)

3) Drop all the rows that have at least one null.

![image](https://user-images.githubusercontent.com/91839403/159949343-40938e48-7f80-4ccf-8e1f-33f0937eb285.png)
![image](https://user-images.githubusercontent.com/91839403/159949471-513d1fdb-faf1-40c1-a014-d364d6c52085.png)

![image](https://user-images.githubusercontent.com/91839403/159949545-9495330f-80fc-4f6f-b538-43d540b01fff.png)

4) All rows removed where coins are not being mined.

![image](https://user-images.githubusercontent.com/91839403/159949872-83ffb137-cf2e-4e13-bf42-e9dbcd34695f.png)

![image](https://user-images.githubusercontent.com/91839403/159949925-f38c0b36-fab3-4303-980e-516522248528.png)

5) The CoinName column is dropped.

![image](https://user-images.githubusercontent.com/91839403/159950045-4e126a07-2590-4603-a188-2f012f1bb180.png)

![image](https://user-images.githubusercontent.com/91839403/159950094-bdf821f4-272f-437e-a003-71384c5248ab.png)

![image](https://user-images.githubusercontent.com/91839403/159950226-1352c642-d952-41f6-a08f-6d2db7d0d874.png)

![image](https://user-images.githubusercontent.com/91839403/159950296-1377f258-b82a-4b05-876c-2c261c7a0784.png)


### Reduce Data Dimensions Using PCA
#### Reduction of Data Dimensions using PCA Actions

1) The PCA algorithm reduces the dimensions of the X DataFrame down to three principal components
2) The pcs_df DataFrame is created and has the following three columns, PC 1, PC 2, and PC 3, and has the index from the crypto_df DataFrame

Results 

1) PCA Algorithm with 3 dimensions

![image](https://user-images.githubusercontent.com/91839403/159951256-94a450d1-c0b4-4266-9a84-cf7c47a12b5b.png)

2) The pcs_df DataFrame is created and has the following three columns, PC 1, PC 2, and PC 3, and has the index from the crypto_df DataFrame.

![image](https://user-images.githubusercontent.com/91839403/159951424-9b54d1d0-e2bb-4dcd-892e-497eabb9c310.png)

![image](https://user-images.githubusercontent.com/91839403/159952257-5f90ce92-5c18-4d78-a95e-1d4a05798484.png)

### Clustering Cryptocurrencies Using K-means
#### The K-means algorithm is used to cluster the cryptocurrencies using the PCA data, where the following steps have been completed:
1) An elbow curve is created using hvPlot to find the best value for K
2) Predictions are made on the K clusters of the cryptocurrencies’ data
3) A new DataFrame is created with the same index as the crypto_df DataFrame and has the following columns:
       Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class
       
1) An elbow curve

![image](https://user-images.githubusercontent.com/91839403/159952762-8ca5c384-7d19-4505-b2e8-408130b305a6.png)

![image](https://user-images.githubusercontent.com/91839403/159953645-21ae32e0-6f1e-465f-bd25-3970de0cd7be.png)

Predictions on the K clusters

![image](https://user-images.githubusercontent.com/91839403/159953850-ca0e58b8-c7a7-4b9d-b1ad-5422215bc4d0.png)


3) A new DataFrame is created with the same index as the crypto_df DataFrame

![image](https://user-images.githubusercontent.com/91839403/159954110-0061320e-4064-4e1a-acfd-ad1c3df07782.png)

![image](https://user-images.githubusercontent.com/91839403/159954271-7be7a441-d3b4-4b2f-b3f9-d6654d0cc43c.png)

### Visualizing Cryptocurrencies Results
####  Visualize the distinct groups that correspond to the three principal components created and create a table with all the currently tradable cryptocurrencies to include the following deliverables:

1) The clusters are plotted using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover
2) A table with tradable cryptocurrencies is created using the hvplot.table() function.
3) The total number of tradable cryptocurrencies is printed
4) A DataFrame is created that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns
5) A hvplot scatter plot is created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class", and it shows the CoinName when you hover over the data point.


1) 3D Plot of clusters with Hover data 

![image](https://user-images.githubusercontent.com/91839403/159955656-4b5fe371-0968-4dc9-be15-a797ff812310.png)

2) Table of tradeable cryptocurrencies

![image](https://user-images.githubusercontent.com/91839403/159955740-228e8b5a-4435-4750-8e0a-bfd94d025908.png)

3) Total number of tradable crypto currencies

![image](https://user-images.githubusercontent.com/91839403/159955948-c6f6ac01-047c-4e81-aaff-56d718ac239e.png)

4)  A DataFrame is created that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns

![image](https://user-images.githubusercontent.com/91839403/159956127-c908c271-fe34-4e41-8715-e5e6fa843785.png)

5) Scatter Plot of "TotalCoinsMined" vs "TotalCoinSupply"

![image](https://user-images.githubusercontent.com/91839403/159956340-007c9ac1-fe36-46fb-a27e-f5446a82510d.png)

