# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset
   
2.check for null values

3.Import kmeans and fit it to the dataset 

4.Plot the graph using elbow method

5.Print the predicted array 

6.Plot the customer segments
 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Madhushri 
RegisterNumber:212224040178
*/
```
```
import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

data["cluster"]=y_pred

df0=data[data["cluster"]==0]

df1=data[data["cluster"]==1]

df2=data[data["cluster"]==2]

df3=data[data["cluster"]==3]

df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()

plt.title("Customer Segment")
```

## Output:
1.DATA.HEAD():

<img width="900" height="304" alt="image" src="https://github.com/user-attachments/assets/27e179ab-1368-4804-841e-9a88837f082a" />

2.DATA.INF0():

<img width="837" height="408" alt="image" src="https://github.com/user-attachments/assets/571d4ef6-d750-430b-a144-96e7d41186f9" />

3.DATA.ISNULL().SUM():

<img width="521" height="216" alt="image" src="https://github.com/user-attachments/assets/93e3100b-04bb-4083-8d06-6ef66c79fc9c" />

4.PLOT USING ELBOW METHOD:

<img width="1029" height="713" alt="image" src="https://github.com/user-attachments/assets/79074efb-4962-403a-adff-762d64c7f36e" />

5.K-MEANS CLUSTERING:

<img width="1033" height="316" alt="image" src="https://github.com/user-attachments/assets/2f0d9035-fc93-4814-86b5-2bac0a88712a" />

6.Y_PRED ARRAY:

<img width="1029" height="309" alt="image" src="https://github.com/user-attachments/assets/6ba4f1e6-d436-490d-8389-850518591b0c" />

7.CUSTOMER SEGMENT:

<img width="1026" height="767" alt="image" src="https://github.com/user-attachments/assets/b1599c12-5647-4e24-9fd3-a98b728ebc3f" />









## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
