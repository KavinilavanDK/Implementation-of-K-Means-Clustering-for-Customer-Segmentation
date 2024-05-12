# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import pandas and matplot libraries.

2.import Kmeans algorithm to solve customer segmentation.

3.Using the for loop cluster the given data

4.Predict the output and plot data graphs.

5.Display the outputs
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: KAVI NILAVAN DK
RegisterNumber:  212223230103
*/

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
#### 1.DATA.HEAD():
![ml 1](https://github.com/KavinilavanDK/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870429/773d3a6e-76ee-4dda-97ba-03c1fcd3e32b)
#### 2.DATA.INF0():
![ml 2](https://github.com/KavinilavanDK/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870429/b9a55127-7e9e-4a96-a8c3-24e8a9522c5e)
#### 3.DATA.ISNULL().SUM():
![ml 3](https://github.com/KavinilavanDK/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870429/334b1514-df15-4ae0-a19c-1c0a6558b677)
#### 4.PLOT USING ELBOW METHOD:
![ml 4](https://github.com/KavinilavanDK/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870429/be6bb945-75ad-44fb-8c4c-48b020d52dd4)
#### 5.K-MEANS CLUSTERING:
![ml 5](https://github.com/KavinilavanDK/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870429/b1226770-38d1-48a2-880f-ba33daf086c5)
#### 6.Y_PRED ARRAY:
![ml 6](https://github.com/KavinilavanDK/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870429/9d78ba85-39d1-40f8-bc9d-84d1d2b074d2)
#### 7.CUSTOMER SEGMENT:
![ml 7](https://github.com/KavinilavanDK/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870429/6dd91d75-12ec-474c-bf79-bb5aaf0343fd)
## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
